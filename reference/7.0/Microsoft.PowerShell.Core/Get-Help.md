---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 10/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-help?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Help
ms.openlocfilehash: 6a8f1379c90b3af97b705266152f9d2407bf0132
ms.sourcegitcommit: b7ff031a12afd04910aeb98345ebee92f5845b0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2020
ms.locfileid: "93195089"
---
# <span data-ttu-id="7f589-103">Get-Help</span><span class="sxs-lookup"><span data-stu-id="7f589-103">Get-Help</span></span>

## <span data-ttu-id="7f589-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="7f589-104">SYNOPSIS</span></span>
<span data-ttu-id="7f589-105">Exibe informações sobre os comandos e conceitos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f589-105">Displays information about PowerShell commands and concepts.</span></span>

## <span data-ttu-id="7f589-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7f589-106">SYNTAX</span></span>

### <span data-ttu-id="7f589-107">AllUsersView (padrão)</span><span class="sxs-lookup"><span data-stu-id="7f589-107">AllUsersView (Default)</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Full] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="7f589-108">DetailedView</span><span class="sxs-lookup"><span data-stu-id="7f589-108">DetailedView</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Detailed] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="7f589-109">Exemplos</span><span class="sxs-lookup"><span data-stu-id="7f589-109">Examples</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Examples] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="7f589-110">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="7f589-110">Parameters</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] -Parameter <String[]>
 [-Component <String[]>] [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="7f589-111">Online</span><span class="sxs-lookup"><span data-stu-id="7f589-111">Online</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] [-Online] [<CommonParameters>]
```

### <span data-ttu-id="7f589-112">ShowWindow</span><span class="sxs-lookup"><span data-stu-id="7f589-112">ShowWindow</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] [-ShowWindow] [<CommonParameters>]
```

## <span data-ttu-id="7f589-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7f589-113">DESCRIPTION</span></span>

<span data-ttu-id="7f589-114">O `Get-Help` cmdlet exibe informações sobre os conceitos e comandos do PowerShell, incluindo cmdlets, funções, comandos de modelo CIM (CIM), fluxos de trabalho, provedores, aliases e scripts.</span><span class="sxs-lookup"><span data-stu-id="7f589-114">The `Get-Help` cmdlet displays information about PowerShell concepts and commands, including cmdlets, functions, Common Information Model (CIM) commands, workflows, providers, aliases, and scripts.</span></span>

<span data-ttu-id="7f589-115">Para obter ajuda para um cmdlet do PowerShell, digite `Get-Help` seguido pelo nome do cmdlet, como: `Get-Help Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="7f589-115">To get help for a PowerShell cmdlet, type `Get-Help` followed by the cmdlet name, such as: `Get-Help Get-Process`.</span></span>

<span data-ttu-id="7f589-116">Os artigos de ajuda conceitual no PowerShell começam com **about_** , como **about_Comparison_Operators** .</span><span class="sxs-lookup"><span data-stu-id="7f589-116">Conceptual help articles in PowerShell begin with **about_** , such as **about_Comparison_Operators** .</span></span> <span data-ttu-id="7f589-117">Para ver todos os artigos **about_** , digite `Get-Help about_*` .</span><span class="sxs-lookup"><span data-stu-id="7f589-117">To see all **about_** articles, type `Get-Help about_*`.</span></span> <span data-ttu-id="7f589-118">Para ver um artigo específico, digite `Get-Help about_<article-name>` , como `Get-Help about_Comparison_Operators` .</span><span class="sxs-lookup"><span data-stu-id="7f589-118">To see a particular article, type `Get-Help about_<article-name>`, such as `Get-Help about_Comparison_Operators`.</span></span>

<span data-ttu-id="7f589-119">Para obter ajuda para um provedor do PowerShell, digite `Get-Help` seguido pelo nome do provedor.</span><span class="sxs-lookup"><span data-stu-id="7f589-119">To get help for a PowerShell provider, type `Get-Help` followed by the provider name.</span></span> <span data-ttu-id="7f589-120">Por exemplo, para obter ajuda para o provedor de certificado, digite `Get-Help Certificate` .</span><span class="sxs-lookup"><span data-stu-id="7f589-120">For example, to get help for the Certificate provider, type `Get-Help Certificate`.</span></span>

<span data-ttu-id="7f589-121">Você também pode digitar `help` ou `man` , que exibe uma tela de texto de cada vez.</span><span class="sxs-lookup"><span data-stu-id="7f589-121">You can also type `help` or `man`, which displays one screen of text at a time.</span></span> <span data-ttu-id="7f589-122">Ou, `<cmdlet-name> -?` , que é idêntico a `Get-Help` , mas funciona apenas para cmdlets.</span><span class="sxs-lookup"><span data-stu-id="7f589-122">Or, `<cmdlet-name> -?`, that is identical to `Get-Help`, but only works for cmdlets.</span></span>

<span data-ttu-id="7f589-123">`Get-Help` Obtém o conteúdo da ajuda que ele exibe dos arquivos de ajuda no seu computador.</span><span class="sxs-lookup"><span data-stu-id="7f589-123">`Get-Help` gets the help content that it displays from help files on your computer.</span></span> <span data-ttu-id="7f589-124">Sem os arquivos de ajuda, o `Get-Help` exibe apenas informações básicas sobre os cmdlets.</span><span class="sxs-lookup"><span data-stu-id="7f589-124">Without the help files, `Get-Help` displays only basic information about cmdlets.</span></span> <span data-ttu-id="7f589-125">Alguns módulos do PowerShell incluem arquivos de ajuda.</span><span class="sxs-lookup"><span data-stu-id="7f589-125">Some PowerShell modules include help files.</span></span> <span data-ttu-id="7f589-126">A partir do PowerShell 3,0, os módulos fornecidos com o sistema operacional Windows não incluem arquivos de ajuda.</span><span class="sxs-lookup"><span data-stu-id="7f589-126">Beginning in PowerShell 3.0, the modules that come with the Windows operating system don't include help files.</span></span> <span data-ttu-id="7f589-127">Para baixar ou atualizar os arquivos de ajuda para um módulo no PowerShell 3,0, use o `Update-Help` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7f589-127">To download or update the help files for a module in PowerShell 3.0, use the `Update-Help` cmdlet.</span></span>

<span data-ttu-id="7f589-128">Você também pode exibir os documentos de ajuda do PowerShell online no Microsoft Docs. Para obter a versão online de um arquivo de ajuda, use o parâmetro **online** , como: `Get-Help Get-Process -Online` .</span><span class="sxs-lookup"><span data-stu-id="7f589-128">You can also view the PowerShell help documents online in the Microsoft Docs. To get the online version of a help file, use the **Online** parameter, such as: `Get-Help Get-Process -Online`.</span></span> <span data-ttu-id="7f589-129">Para ler toda a documentação do PowerShell, consulte a [documentação](/powershell)do Microsoft docs PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f589-129">To read all the PowerShell documentation, see the Microsoft Docs [PowerShell Documentation](/powershell).</span></span>

<span data-ttu-id="7f589-130">Se você digitar `Get-Help` seguido pelo nome exato de um artigo de ajuda ou por uma palavra exclusiva para um artigo de ajuda, `Get-Help` o exibirá o conteúdo do artigo.</span><span class="sxs-lookup"><span data-stu-id="7f589-130">If you type `Get-Help` followed by the exact name of a help article, or by a word unique to a help article, `Get-Help` displays the article's content.</span></span> <span data-ttu-id="7f589-131">Se você especificar o nome exato de um alias de comando, `Get-Help` o exibirá a ajuda do comando original.</span><span class="sxs-lookup"><span data-stu-id="7f589-131">If you specify the exact name of a command alias, `Get-Help` displays the help for the original command.</span></span> <span data-ttu-id="7f589-132">Se você inserir um padrão de palavra ou palavra que aparece em vários títulos de artigos `Get-Help` da ajuda, o exibirá uma lista dos títulos correspondentes.</span><span class="sxs-lookup"><span data-stu-id="7f589-132">If you enter a word or word pattern that appears in several help article titles, `Get-Help` displays a list of the matching titles.</span></span> <span data-ttu-id="7f589-133">Se você inserir qualquer texto que não apareça em títulos de artigos de ajuda, `Get-Help` o exibirá uma lista de artigos que incluem esse texto em seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="7f589-133">If you enter any text that doesn't appear in any help article titles, `Get-Help` displays a list of articles that include that text in their contents.</span></span>

<span data-ttu-id="7f589-134">`Get-Help` pode obter artigos de ajuda para todos os idiomas e localidades com suporte.</span><span class="sxs-lookup"><span data-stu-id="7f589-134">`Get-Help` can get help articles for all supported languages and locales.</span></span> <span data-ttu-id="7f589-135">`Get-Help` o primeiro procura arquivos de ajuda na localidade definida para Windows, em seguida, na localidade pai, como **pt** para **pt-br** e, em seguida, em uma localidade de fallback.</span><span class="sxs-lookup"><span data-stu-id="7f589-135">`Get-Help` first looks for help files in the locale set for Windows, then in the parent locale, such as **pt** for **pt-BR** , and then in a fallback locale.</span></span> <span data-ttu-id="7f589-136">A partir do PowerShell 3,0, se o `Get-Help` não encontrar ajuda na localidade de fallback, ele procurará artigos de ajuda em inglês, **en-US** , antes de retornar uma mensagem de erro ou exibir a ajuda gerada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7f589-136">Beginning in PowerShell 3.0, if `Get-Help` doesn't find help in the fallback locale, it looks for help articles in English, **en-US** , before it returns an error message or displaying autogenerated help.</span></span>

<span data-ttu-id="7f589-137">Para obter informações sobre os símbolos `Get-Help` exibidos no diagrama de sintaxe de comando, consulte [about_Command_Syntax](./About/about_Command_Syntax.md).</span><span class="sxs-lookup"><span data-stu-id="7f589-137">For information about the symbols that `Get-Help` displays in the command syntax diagram, see [about_Command_Syntax](./About/about_Command_Syntax.md).</span></span>
<span data-ttu-id="7f589-138">Para obter informações sobre atributos de parâmetro, como **Required** e **Position** , consulte [about_Parameters](./About/about_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="7f589-138">For information about parameter attributes, such as **Required** and **Position** , see [about_Parameters](./About/about_Parameters.md).</span></span>

>[!NOTE]
> <span data-ttu-id="7f589-139">No PowerShell 3,0 e no PowerShell 4,0, `Get-Help` o **About** não consegue encontrar artigos em módulos, a menos que o módulo seja importado para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7f589-139">In PowerShell 3.0 and PowerShell 4.0, `Get-Help` can't find **About** articles in modules unless the module is imported into the current session.</span></span> <span data-ttu-id="7f589-140">Este é um problema conhecido.</span><span class="sxs-lookup"><span data-stu-id="7f589-140">This is a known issue.</span></span> <span data-ttu-id="7f589-141">Para obter **informações sobre** artigos em um módulo, importe o módulo usando o `Import-Module` cmdlet ou executando um cmdlet que está incluído no módulo.</span><span class="sxs-lookup"><span data-stu-id="7f589-141">To get **About** articles in a module, import the module, either by using the `Import-Module` cmdlet or by running a cmdlet that's included in the module.</span></span>

## <span data-ttu-id="7f589-142">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="7f589-142">EXAMPLES</span></span>

### <span data-ttu-id="7f589-143">Exemplo 1: exibir informações básicas de ajuda sobre um cmdlet</span><span class="sxs-lookup"><span data-stu-id="7f589-143">Example 1: Display basic help information about a cmdlet</span></span>

<span data-ttu-id="7f589-144">Esses exemplos exibem informações básicas de ajuda sobre o `Format-Table` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7f589-144">These examples display basic help information about the `Format-Table` cmdlet.</span></span>

```powershell
Get-Help Format-Table
Get-Help -Name Format-Table
Format-Table -?
```

<span data-ttu-id="7f589-145">`Get-Help <cmdlet-name>` é a sintaxe mais simples e padrão do `Get-Help` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7f589-145">`Get-Help <cmdlet-name>` is the simplest and default syntax of `Get-Help` cmdlet.</span></span> <span data-ttu-id="7f589-146">Você pode omitir o parâmetro **Name** .</span><span class="sxs-lookup"><span data-stu-id="7f589-146">You can omit the **Name** parameter.</span></span>

<span data-ttu-id="7f589-147">A sintaxe `<cmdlet-name> -?` funciona apenas para cmdlets.</span><span class="sxs-lookup"><span data-stu-id="7f589-147">The syntax `<cmdlet-name> -?` works only for cmdlets.</span></span>

### <span data-ttu-id="7f589-148">Exemplo 2: exibir informações básicas uma página por vez</span><span class="sxs-lookup"><span data-stu-id="7f589-148">Example 2: Display basic information one page at a time</span></span>

<span data-ttu-id="7f589-149">Esses exemplos exibem informações básicas de ajuda sobre o `Format-Table` cmdlet uma página por vez.</span><span class="sxs-lookup"><span data-stu-id="7f589-149">These examples display basic help information about the `Format-Table` cmdlet one page at a time.</span></span>

```powershell
help Format-Table
man Format-Table
Get-Help Format-Table | Out-Host -Paging
```

<span data-ttu-id="7f589-150">`help` é uma função que executa `Get-Help` o cmdlet internamente e exibe o resultado uma página por vez.</span><span class="sxs-lookup"><span data-stu-id="7f589-150">`help` is a function that runs `Get-Help` cmdlet internally and displays the result one page at a time.</span></span>

<span data-ttu-id="7f589-151">`man` é um alias para a `help` função.</span><span class="sxs-lookup"><span data-stu-id="7f589-151">`man` is an alias for the `help` function.</span></span>

<span data-ttu-id="7f589-152">`Get-Help Format-Table` envia o objeto para baixo do pipeline.</span><span class="sxs-lookup"><span data-stu-id="7f589-152">`Get-Help Format-Table` sends the object down the pipeline.</span></span> <span data-ttu-id="7f589-153">`Out-Host -Paging` recebe a saída do pipeline e exibe uma página por vez.</span><span class="sxs-lookup"><span data-stu-id="7f589-153">`Out-Host -Paging` receives the output from the pipeline and displays it one page at a time.</span></span> <span data-ttu-id="7f589-154">Para obter mais informações, consulte [Out-Host](Out-Host.md).</span><span class="sxs-lookup"><span data-stu-id="7f589-154">For more information, see [Out-Host](Out-Host.md).</span></span>

### <span data-ttu-id="7f589-155">Exemplo 3: exibir mais informações para um cmdlet</span><span class="sxs-lookup"><span data-stu-id="7f589-155">Example 3: Display more information for a cmdlet</span></span>

<span data-ttu-id="7f589-156">Esses exemplos exibem informações de ajuda mais detalhadas sobre o `Format-Table` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7f589-156">These examples display more detailed help information about the `Format-Table` cmdlet.</span></span>

```powershell
Get-Help Format-Table -Detailed
Get-Help Format-Table -Full
```

<span data-ttu-id="7f589-157">O parâmetro **detailed** exibe a exibição detalhada do artigo de ajuda que inclui descrições e exemplos de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="7f589-157">The **Detailed** parameter displays the help article's detailed view that includes parameter descriptions and examples.</span></span>

<span data-ttu-id="7f589-158">O parâmetro **Full** exibe a exibição completa do artigo de ajuda que inclui descrições de parâmetro, exemplos, tipos de objeto de entrada e saída e observações adicionais.</span><span class="sxs-lookup"><span data-stu-id="7f589-158">The **Full** parameter displays the help article's full view that includes parameter descriptions, examples, input and output object types, and additional notes.</span></span>

<span data-ttu-id="7f589-159">Os parâmetros **detalhados** e **completos** são efetivos apenas para os comandos que têm arquivos de ajuda instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="7f589-159">The **Detailed** and **Full** parameters are effective only for the commands that have help files installed on the computer.</span></span> <span data-ttu-id="7f589-160">Os parâmetros não são eficazes para os artigos de ajuda conceitual ( **about_** ).</span><span class="sxs-lookup"><span data-stu-id="7f589-160">The parameters aren't effective for the conceptual ( **about_** ) help articles.</span></span>

### <span data-ttu-id="7f589-161">Exemplo 4: exibir as partes selecionadas de um cmdlet usando parâmetros</span><span class="sxs-lookup"><span data-stu-id="7f589-161">Example 4: Display selected parts of a cmdlet by using parameters</span></span>

<span data-ttu-id="7f589-162">Esses exemplos exibem as partes selecionadas da `Format-Table` ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7f589-162">These examples display selected portions of the `Format-Table` cmdlet help.</span></span>

```powershell
Get-Help Format-Table -Examples
Get-Help Format-Table -Parameter *
Get-Help Format-Table -Parameter GroupBy
```

<span data-ttu-id="7f589-163">O parâmetro de **exemplos** exibe as seções **nome** e **Sinopse** do arquivo de ajuda e todos os exemplos.</span><span class="sxs-lookup"><span data-stu-id="7f589-163">The **Examples** parameter displays the help file's **NAME** and **SYNOPSIS** sections, and all the Examples.</span></span> <span data-ttu-id="7f589-164">Você não pode especificar um número de exemplo porque o parâmetro de **exemplos** é um parâmetro de opção.</span><span class="sxs-lookup"><span data-stu-id="7f589-164">You can't specify an Example number because the **Examples** parameter is a switch parameter.</span></span>

<span data-ttu-id="7f589-165">O parâmetro **Parameter** exibe apenas as descrições dos parâmetros especificados.</span><span class="sxs-lookup"><span data-stu-id="7f589-165">The **Parameter** parameter displays only the descriptions of the specified parameters.</span></span> <span data-ttu-id="7f589-166">Se você especificar apenas o `*` caractere curinga asterisco (), ele exibirá as descrições de todos os parâmetros.</span><span class="sxs-lookup"><span data-stu-id="7f589-166">If you specify only the asterisk (`*`) wildcard character, it displays the descriptions of all parameters.</span></span>
<span data-ttu-id="7f589-167">Quando o **parâmetro** especifica um nome de parâmetro, como **GroupBy** , as informações sobre esse parâmetro são mostradas.</span><span class="sxs-lookup"><span data-stu-id="7f589-167">When **Parameter** specifies a parameter name such as **GroupBy** , information about that parameter is shown.</span></span>

<span data-ttu-id="7f589-168">Esses parâmetros não são eficazes para os artigos de ajuda conceitual ( **about_** ).</span><span class="sxs-lookup"><span data-stu-id="7f589-168">These parameters aren't effective for the conceptual ( **about_** ) help articles.</span></span>

### <span data-ttu-id="7f589-169">Exemplo 5: exibir a versão online da ajuda</span><span class="sxs-lookup"><span data-stu-id="7f589-169">Example 5: Display online version of help</span></span>

<span data-ttu-id="7f589-170">Este exemplo exibe a versão online do artigo de ajuda para o `Format-Table` cmdlet no navegador da Web padrão.</span><span class="sxs-lookup"><span data-stu-id="7f589-170">This example displays the online version of the help article for the `Format-Table` cmdlet in your default web browser.</span></span>

```powershell
Get-Help Format-Table -Online
```

### <span data-ttu-id="7f589-171">Exemplo 6: exibir a ajuda sobre o sistema de ajuda</span><span class="sxs-lookup"><span data-stu-id="7f589-171">Example 6: Display help about the help system</span></span>

<span data-ttu-id="7f589-172">O `Get-Help` cmdlet sem parâmetros exibe informações sobre o sistema de ajuda do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f589-172">The `Get-Help` cmdlet without parameters displays information about the PowerShell help system.</span></span>

```powershell
Get-Help
```

### <span data-ttu-id="7f589-173">Exemplo 7: Exibir artigos de ajuda disponíveis</span><span class="sxs-lookup"><span data-stu-id="7f589-173">Example 7: Display available help articles</span></span>

<span data-ttu-id="7f589-174">Este exemplo exibe uma lista de todos os artigos de ajuda disponíveis no seu computador.</span><span class="sxs-lookup"><span data-stu-id="7f589-174">This example displays a list of all help articles available on your computer.</span></span>

```powershell
Get-Help *
```

### <span data-ttu-id="7f589-175">Exemplo 8: exibir uma lista de artigos conceituais</span><span class="sxs-lookup"><span data-stu-id="7f589-175">Example 8: Display a list of conceptual articles</span></span>

<span data-ttu-id="7f589-176">Este exemplo exibe uma lista dos artigos conceituais incluídos na ajuda do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f589-176">This example displays a list of the conceptual articles included in PowerShell help.</span></span> <span data-ttu-id="7f589-177">Todos esses artigos começam com os caracteres **about_** .</span><span class="sxs-lookup"><span data-stu-id="7f589-177">All these articles begin with the characters **about_** .</span></span> <span data-ttu-id="7f589-178">Para exibir um arquivo de ajuda específico, digite `Get-Help \<about_article-name\>` , por exemplo, `Get-Help about_Signing` .</span><span class="sxs-lookup"><span data-stu-id="7f589-178">To display a particular help file, type `Get-Help \<about_article-name\>`, for example, `Get-Help about_Signing`.</span></span>

<span data-ttu-id="7f589-179">Somente os artigos conceituais que têm arquivos de ajuda instalados no computador são exibidos.</span><span class="sxs-lookup"><span data-stu-id="7f589-179">Only the conceptual articles that have help files installed on your computer are displayed.</span></span> <span data-ttu-id="7f589-180">Para obter informações sobre como baixar e instalar arquivos de ajuda no PowerShell 3,0, consulte [Update-Help](Update-Help.md).</span><span class="sxs-lookup"><span data-stu-id="7f589-180">For information about downloading and installing help files in PowerShell 3.0, see [Update-Help](Update-Help.md).</span></span>

```powershell
Get-Help about_*
```

### <span data-ttu-id="7f589-181">Exemplo 9: Pesquisar uma palavra na ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="7f589-181">Example 9: Search for a word in cmdlet help</span></span>

<span data-ttu-id="7f589-182">Este exemplo mostra como pesquisar uma palavra em um artigo de ajuda de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7f589-182">This example shows how to search for a word in a cmdlet help article.</span></span>

```powershell
Get-Help Add-Member -Full | Out-String -Stream | Select-String -Pattern Clixml
```

```Output
the Export-Clixml cmdlet to save the instance of the object, including the additional members...
can use the Import-Clixml cmdlet to re-create the instance of the object from the information...
Export-Clixml
Import-Clixml
```

<span data-ttu-id="7f589-183">`Get-Help` usa o parâmetro **Full** para obter informações de ajuda para o `Add-Member` .</span><span class="sxs-lookup"><span data-stu-id="7f589-183">`Get-Help` uses the **Full** parameter to get help information for `Add-Member`.</span></span> <span data-ttu-id="7f589-184">O objeto **MamlCommandHelpInfo** é enviado pelo pipeline.</span><span class="sxs-lookup"><span data-stu-id="7f589-184">The **MamlCommandHelpInfo** object is sent down the pipeline.</span></span> <span data-ttu-id="7f589-185">`Out-String` usa o parâmetro **Stream** para converter o objeto em uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7f589-185">`Out-String` uses the **Stream** parameter to convert the object into a string.</span></span> <span data-ttu-id="7f589-186">`Select-String` usa o parâmetro **Pattern** para pesquisar a cadeia de caracteres de **Clixml** .</span><span class="sxs-lookup"><span data-stu-id="7f589-186">`Select-String` uses the **Pattern** parameter to search the string for **Clixml** .</span></span>

### <span data-ttu-id="7f589-187">Exemplo 10: exibir uma lista de artigos que incluem uma palavra</span><span class="sxs-lookup"><span data-stu-id="7f589-187">Example 10: Display a list of articles that include a word</span></span>

<span data-ttu-id="7f589-188">Este exemplo exibe uma lista de artigos que incluem a palavra **Remoting** .</span><span class="sxs-lookup"><span data-stu-id="7f589-188">This example displays a list of articles that include the word **remoting** .</span></span>

<span data-ttu-id="7f589-189">Quando você insere uma palavra que não aparece em nenhum título de artigo, `Get-Help` o exibe uma lista de artigos que incluem essa palavra.</span><span class="sxs-lookup"><span data-stu-id="7f589-189">When you enter a word that doesn't appear in any article title, `Get-Help` displays a list of articles that include that word.</span></span>

```powershell
Get-Help -Name remoting
```

```Output
Name                              Category  Module                    Synopsis
----                              --------  ------                    --------
Install-PowerShellRemoting.ps1    External                            Install-PowerShellRemoting.ps1
Disable-PSRemoting                Cmdlet    Microsoft.PowerShell.Core Prevents remote users...
Enable-PSRemoting                 Cmdlet    Microsoft.PowerShell.Core Configures the computer...
```

### <span data-ttu-id="7f589-190">Exemplo 11: exibir a ajuda específica do provedor</span><span class="sxs-lookup"><span data-stu-id="7f589-190">Example 11: Display provider-specific help</span></span>

<span data-ttu-id="7f589-191">Este exemplo mostra duas maneiras de obter a ajuda específica do provedor para o `Get-Item` .</span><span class="sxs-lookup"><span data-stu-id="7f589-191">This example shows two ways of getting the provider-specific help for `Get-Item`.</span></span> <span data-ttu-id="7f589-192">Esses comandos obtêm ajuda que explica como usar o `Get-Item` cmdlet no nó **DataCollection** do provedor de SQL Server do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f589-192">These commands get help that explains how to use the `Get-Item` cmdlet in the PowerShell SQL Server provider's **DataCollection** node.</span></span>

<span data-ttu-id="7f589-193">O primeiro exemplo usa o `Get-Help` parâmetro **Path** para especificar o caminho do provedor de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7f589-193">The first example uses the `Get-Help` **Path** parameter to specify the SQL Server provider's path.</span></span>
<span data-ttu-id="7f589-194">Como o caminho do provedor é especificado, você pode executar o comando de qualquer local de caminho.</span><span class="sxs-lookup"><span data-stu-id="7f589-194">Because the provider's path is specified, you can run the command from any path location.</span></span>

<span data-ttu-id="7f589-195">O segundo exemplo usa `Set-Location` para navegar até o caminho do provedor de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7f589-195">The second example uses `Set-Location` to navigate to the SQL Server provider's path.</span></span> <span data-ttu-id="7f589-196">Nesse local, o parâmetro **path** não é necessário para `Get-Help` que o obtenha a ajuda específica do provedor.</span><span class="sxs-lookup"><span data-stu-id="7f589-196">From that location, the **Path** parameter isn't needed for `Get-Help` to get the provider-specific help.</span></span>

```powershell
Get-Help Get-Item -Path SQLSERVER:\DataCollection
```

```Output
NAME

    Get-Item

SYNOPSIS

    Gets a collection of Server objects for the local computer and any computers

    to which you have made a SQL Server PowerShell connection.
    ...
```

```powershell
Set-Location SQLSERVER:\DataCollection
SQLSERVER:\DataCollection> Get-Help Get-Item
```

```Output
NAME

    Get-Item

SYNOPSIS

    Gets a collection of Server objects for the local computer and any computers

    to which you have made a SQL Server PowerShell connection.
    ...
```

### <span data-ttu-id="7f589-197">Exemplo 12: exibir a ajuda para um script</span><span class="sxs-lookup"><span data-stu-id="7f589-197">Example 12: Display help for a script</span></span>

<span data-ttu-id="7f589-198">Este exemplo obtém ajuda para o `MyScript.ps1 script` .</span><span class="sxs-lookup"><span data-stu-id="7f589-198">This example gets help for the `MyScript.ps1 script`.</span></span> <span data-ttu-id="7f589-199">Para obter informações sobre como escrever ajuda para suas funções e scripts, consulte [about_Comment_Based_Help](./About/about_Comment_Based_Help.md).</span><span class="sxs-lookup"><span data-stu-id="7f589-199">For information about how to write help for your functions and scripts, see [about_Comment_Based_Help](./About/about_Comment_Based_Help.md).</span></span>

```powershell
Get-Help -Name C:\PS-Test\MyScript.ps1
```

## <span data-ttu-id="7f589-200">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7f589-200">PARAMETERS</span></span>

### <span data-ttu-id="7f589-201">-Categoria</span><span class="sxs-lookup"><span data-stu-id="7f589-201">-Category</span></span>

<span data-ttu-id="7f589-202">Exibe ajuda apenas para itens na categoria especificada e seus aliases.</span><span class="sxs-lookup"><span data-stu-id="7f589-202">Displays help only for items in the specified category and their aliases.</span></span> <span data-ttu-id="7f589-203">Os artigos conceituais estão na categoria **HelpFile** .</span><span class="sxs-lookup"><span data-stu-id="7f589-203">Conceptual articles are in the **HelpFile** category.</span></span>

<span data-ttu-id="7f589-204">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="7f589-204">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="7f589-205">Alias</span><span class="sxs-lookup"><span data-stu-id="7f589-205">Alias</span></span>
- <span data-ttu-id="7f589-206">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="7f589-206">Cmdlet</span></span>
- <span data-ttu-id="7f589-207">Provedor</span><span class="sxs-lookup"><span data-stu-id="7f589-207">Provider</span></span>
- <span data-ttu-id="7f589-208">Geral</span><span class="sxs-lookup"><span data-stu-id="7f589-208">General</span></span>
- <span data-ttu-id="7f589-209">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="7f589-209">FAQ</span></span>
- <span data-ttu-id="7f589-210">Glossário</span><span class="sxs-lookup"><span data-stu-id="7f589-210">Glossary</span></span>
- <span data-ttu-id="7f589-211">HelpFile</span><span class="sxs-lookup"><span data-stu-id="7f589-211">HelpFile</span></span>
- <span data-ttu-id="7f589-212">ScriptCommand</span><span class="sxs-lookup"><span data-stu-id="7f589-212">ScriptCommand</span></span>
- <span data-ttu-id="7f589-213">Função</span><span class="sxs-lookup"><span data-stu-id="7f589-213">Function</span></span>
- <span data-ttu-id="7f589-214">Filtrar</span><span class="sxs-lookup"><span data-stu-id="7f589-214">Filter</span></span>
- <span data-ttu-id="7f589-215">ExternalScript</span><span class="sxs-lookup"><span data-stu-id="7f589-215">ExternalScript</span></span>
- <span data-ttu-id="7f589-216">Tudo</span><span class="sxs-lookup"><span data-stu-id="7f589-216">All</span></span>
- <span data-ttu-id="7f589-217">Defaulthelp</span><span class="sxs-lookup"><span data-stu-id="7f589-217">DefaultHelp</span></span>
- <span data-ttu-id="7f589-218">Fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="7f589-218">Workflow</span></span>
- <span data-ttu-id="7f589-219">DscResource</span><span class="sxs-lookup"><span data-stu-id="7f589-219">DscResource</span></span>
- <span data-ttu-id="7f589-220">Classe</span><span class="sxs-lookup"><span data-stu-id="7f589-220">Class</span></span>
- <span data-ttu-id="7f589-221">Configuração</span><span class="sxs-lookup"><span data-stu-id="7f589-221">Configuration</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Alias, Cmdlet, Provider, General, FAQ, Glossary, HelpFile, ScriptCommand, Function, Filter, ExternalScript, All, DefaultHelp, Workflow, DscResource, Class, Configuration

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7f589-222">-Componente</span><span class="sxs-lookup"><span data-stu-id="7f589-222">-Component</span></span>

<span data-ttu-id="7f589-223">Exibe comandos com o valor do componente especificado, como o **Exchange** .</span><span class="sxs-lookup"><span data-stu-id="7f589-223">Displays commands with the specified component value, such as **Exchange** .</span></span> <span data-ttu-id="7f589-224">Insira um nome de componente.</span><span class="sxs-lookup"><span data-stu-id="7f589-224">Enter a component name.</span></span>
<span data-ttu-id="7f589-225">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="7f589-225">Wildcard characters are permitted.</span></span> <span data-ttu-id="7f589-226">Esse parâmetro não tem nenhum efeito em exibições de ajuda conceitual ( **About_** ).</span><span class="sxs-lookup"><span data-stu-id="7f589-226">This parameter has no effect on displays of conceptual ( **About_** ) help.</span></span>

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

### <span data-ttu-id="7f589-227">-Detailed</span><span class="sxs-lookup"><span data-stu-id="7f589-227">-Detailed</span></span>

<span data-ttu-id="7f589-228">Adiciona descrições de parâmetro e exemplos à exibição de ajuda básica.</span><span class="sxs-lookup"><span data-stu-id="7f589-228">Adds parameter descriptions and examples to the basic help display.</span></span> <span data-ttu-id="7f589-229">Esse parâmetro só será eficaz quando os arquivos de ajuda estiverem instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="7f589-229">This parameter is effective only when the help files are installed on the computer.</span></span> <span data-ttu-id="7f589-230">Ele não tem nenhum efeito nas exibições da ajuda conceitual ( **About_** ).</span><span class="sxs-lookup"><span data-stu-id="7f589-230">It has no effect on displays of conceptual ( **About_** ) help.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DetailedView
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7f589-231">-Examples</span><span class="sxs-lookup"><span data-stu-id="7f589-231">-Examples</span></span>

<span data-ttu-id="7f589-232">Exibe apenas o nome, sinopse e exemplos.</span><span class="sxs-lookup"><span data-stu-id="7f589-232">Displays only the name, synopsis, and examples.</span></span> <span data-ttu-id="7f589-233">Para exibir apenas os exemplos, digite `(Get-Help \<cmdlet-name\>).Examples` .</span><span class="sxs-lookup"><span data-stu-id="7f589-233">To display only the examples, type `(Get-Help \<cmdlet-name\>).Examples`.</span></span>

<span data-ttu-id="7f589-234">Esse parâmetro só será eficaz quando os arquivos de ajuda estiverem instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="7f589-234">This parameter is effective only when the help files are installed on the computer.</span></span> <span data-ttu-id="7f589-235">Ele não tem nenhum efeito nas exibições da ajuda conceitual ( **About_** ).</span><span class="sxs-lookup"><span data-stu-id="7f589-235">It has no effect on displays of conceptual ( **About_** ) help.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Examples
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7f589-236">-Full</span><span class="sxs-lookup"><span data-stu-id="7f589-236">-Full</span></span>

<span data-ttu-id="7f589-237">Exibe o artigo de ajuda inteiro de um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7f589-237">Displays the entire help article for a cmdlet.</span></span> <span data-ttu-id="7f589-238">**Completo** inclui descrições de parâmetro e atributos, exemplos, tipos de objeto de entrada e saída e observações adicionais.</span><span class="sxs-lookup"><span data-stu-id="7f589-238">**Full** includes parameter descriptions and attributes, examples, input and output object types, and additional notes.</span></span>

<span data-ttu-id="7f589-239">Esse parâmetro só será eficaz quando os arquivos de ajuda estiverem instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="7f589-239">This parameter is effective only when the help files are installed on the computer.</span></span> <span data-ttu-id="7f589-240">Ele não tem nenhum efeito nas exibições da ajuda conceitual ( **About_** ).</span><span class="sxs-lookup"><span data-stu-id="7f589-240">It has no effect on displays of conceptual ( **About_** ) help.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AllUsersView
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7f589-241">-Funcionalidade</span><span class="sxs-lookup"><span data-stu-id="7f589-241">-Functionality</span></span>

<span data-ttu-id="7f589-242">Exibe ajuda para os itens com a funcionalidade especificada.</span><span class="sxs-lookup"><span data-stu-id="7f589-242">Displays help for items with the specified functionality.</span></span> <span data-ttu-id="7f589-243">Insira a funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="7f589-243">Enter the functionality.</span></span> <span data-ttu-id="7f589-244">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="7f589-244">Wildcard characters are permitted.</span></span> <span data-ttu-id="7f589-245">Esse parâmetro não tem nenhum efeito em exibições de ajuda conceitual ( **About_** ).</span><span class="sxs-lookup"><span data-stu-id="7f589-245">This parameter has no effect on displays of conceptual ( **About_** ) help.</span></span>

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

### <span data-ttu-id="7f589-246">-Name</span><span class="sxs-lookup"><span data-stu-id="7f589-246">-Name</span></span>

<span data-ttu-id="7f589-247">Obtém ajuda sobre o comando ou conceito especificado.</span><span class="sxs-lookup"><span data-stu-id="7f589-247">Gets help about the specified command or concept.</span></span> <span data-ttu-id="7f589-248">Insira o nome de um cmdlet, uma função, um provedor, um script ou um fluxo de trabalho, como `Get-Member` um nome de artigo conceitual, como `about_Objects` , ou um alias, como `ls` .</span><span class="sxs-lookup"><span data-stu-id="7f589-248">Enter the name of a cmdlet, function, provider, script, or workflow, such as `Get-Member`, a conceptual article name, such as `about_Objects`, or an alias, such as `ls`.</span></span> <span data-ttu-id="7f589-249">Caracteres curinga são permitidos em nomes de cmdlet e de provedor, mas você não pode usar caracteres curinga para localizar os nomes dos artigos de ajuda de função e de script.</span><span class="sxs-lookup"><span data-stu-id="7f589-249">Wildcard characters are permitted in cmdlet and provider names, but you can't use wildcard characters to find the names of function help and script help articles.</span></span>

<span data-ttu-id="7f589-250">Para obter ajuda para um script que não está localizado em um caminho listado na variável de `$env:Path` ambiente, digite o caminho e o nome do arquivo do script.</span><span class="sxs-lookup"><span data-stu-id="7f589-250">To get help for a script that isn't located in a path that's listed in the `$env:Path` environment variable, type the script's path and file name.</span></span>

<span data-ttu-id="7f589-251">Se você inserir o nome exato de um artigo de ajuda, `Get-Help` o exibirá o conteúdo do artigo.</span><span class="sxs-lookup"><span data-stu-id="7f589-251">If you enter the exact name of a help article, `Get-Help` displays the article contents.</span></span>

<span data-ttu-id="7f589-252">Se você inserir um padrão de palavra ou palavra que aparece em vários títulos de artigos `Get-Help` da ajuda, o exibirá uma lista dos títulos correspondentes.</span><span class="sxs-lookup"><span data-stu-id="7f589-252">If you enter a word or word pattern that appears in several help article titles, `Get-Help` displays a list of the matching titles.</span></span>

<span data-ttu-id="7f589-253">Se você inserir qualquer texto que não corresponda a nenhum título de artigo `Get-Help` da ajuda, o exibirá uma lista de artigos que incluem esse texto em seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="7f589-253">If you enter any text that doesn't match any help article titles, `Get-Help` displays a list of articles that include that text in their contents.</span></span>

<span data-ttu-id="7f589-254">Os nomes dos artigos conceituais, como `about_Objects` , devem ser inseridos em inglês, mesmo em versões do PowerShell que não estejam em inglês.</span><span class="sxs-lookup"><span data-stu-id="7f589-254">The names of conceptual articles, such as `about_Objects`, must be entered in English, even in non-English versions of PowerShell.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="7f589-255">-Online</span><span class="sxs-lookup"><span data-stu-id="7f589-255">-Online</span></span>

<span data-ttu-id="7f589-256">Exibe a versão online de um artigo de ajuda no navegador padrão.</span><span class="sxs-lookup"><span data-stu-id="7f589-256">Displays the online version of a help article in the default browser.</span></span> <span data-ttu-id="7f589-257">Esse parâmetro é válido somente para artigos de ajuda de cmdlet, função, fluxo de trabalho e script.</span><span class="sxs-lookup"><span data-stu-id="7f589-257">This parameter is valid only for cmdlet, function, workflow, and script help articles.</span></span> <span data-ttu-id="7f589-258">Você não pode usar o parâmetro **online** com `Get-Help` em uma sessão remota.</span><span class="sxs-lookup"><span data-stu-id="7f589-258">You can't use the **Online** parameter with `Get-Help` in a remote session.</span></span>

<span data-ttu-id="7f589-259">Para obter informações sobre como dar suporte a esse recurso nos artigos de ajuda que você escreve, consulte [about_Comment_Based_Help](./About/about_Comment_Based_Help.md)e [suporte à ajuda online](/powershell/scripting/developer/module/supporting-online-help)e [como escrever ajuda para cmdlets do PowerShell](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span><span class="sxs-lookup"><span data-stu-id="7f589-259">For information about supporting this feature in help articles that you write, see [about_Comment_Based_Help](./About/about_Comment_Based_Help.md), and [Supporting Online Help](/powershell/scripting/developer/module/supporting-online-help), and [Writing Help for PowerShell Cmdlets](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Online
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7f589-260">Parâmetros do </span><span class="sxs-lookup"><span data-stu-id="7f589-260">-Parameter</span></span>

<span data-ttu-id="7f589-261">Exibe apenas as descrições detalhadas dos parâmetros especificados.</span><span class="sxs-lookup"><span data-stu-id="7f589-261">Displays only the detailed descriptions of the specified parameters.</span></span> <span data-ttu-id="7f589-262">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="7f589-262">Wildcards are permitted.</span></span> <span data-ttu-id="7f589-263">Esse parâmetro não tem nenhum efeito em exibições de ajuda conceitual ( **About_** ).</span><span class="sxs-lookup"><span data-stu-id="7f589-263">This parameter has no effect on displays of conceptual ( **About_** ) help.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Parameters
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="7f589-264">-Path</span><span class="sxs-lookup"><span data-stu-id="7f589-264">-Path</span></span>

<span data-ttu-id="7f589-265">Obtém ajuda que explica como o cmdlet funciona no caminho do provedor especificado.</span><span class="sxs-lookup"><span data-stu-id="7f589-265">Gets help that explains how the cmdlet works in the specified provider path.</span></span> <span data-ttu-id="7f589-266">Insira um caminho do provedor do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f589-266">Enter a PowerShell provider path.</span></span>

<span data-ttu-id="7f589-267">Esse parâmetro Obtém uma versão personalizada de um artigo de ajuda de cmdlet que explica como o cmdlet funciona no caminho do provedor do PowerShell especificado.</span><span class="sxs-lookup"><span data-stu-id="7f589-267">This parameter gets a customized version of a cmdlet help article that explains how the cmdlet works in the specified PowerShell provider path.</span></span> <span data-ttu-id="7f589-268">Esse parâmetro é eficaz apenas para obter ajuda sobre um cmdlet de provedor e somente quando o provedor inclui uma versão personalizada do artigo de ajuda do cmdlet do provedor em seu arquivo de ajuda.</span><span class="sxs-lookup"><span data-stu-id="7f589-268">This parameter is effective only for help about a provider cmdlet and only when the provider includes a custom version of the provider cmdlet help article in its help file.</span></span> <span data-ttu-id="7f589-269">Para usar este parâmetro, instale o arquivo de ajuda para o módulo que inclui o provedor.</span><span class="sxs-lookup"><span data-stu-id="7f589-269">To use this parameter, install the help file for the module that includes the provider.</span></span>

<span data-ttu-id="7f589-270">Para ver a ajuda do cmdlet personalizado para um caminho do provedor, acesse o local do caminho do provedor e insira um `Get-Help` comando ou, em qualquer local do caminho, use o parâmetro **Path** de `Get-Help` para especificar o caminho do provedor.</span><span class="sxs-lookup"><span data-stu-id="7f589-270">To see the custom cmdlet help for a provider path, go to the provider path location and enter a `Get-Help` command or, from any path location, use the **Path** parameter of `Get-Help` to specify the provider path.</span></span> <span data-ttu-id="7f589-271">Você também pode encontrar a ajuda online do cmdlet na seção de ajuda do provedor dos artigos de ajuda.</span><span class="sxs-lookup"><span data-stu-id="7f589-271">You can also find custom cmdlet help online in the provider help section of the help articles.</span></span>

<span data-ttu-id="7f589-272">Para obter mais informações sobre provedores do PowerShell, consulte [about_Providers](./About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="7f589-272">For more information about PowerShell providers, see [about_Providers](./About/about_Providers.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="7f589-273">-Função</span><span class="sxs-lookup"><span data-stu-id="7f589-273">-Role</span></span>

<span data-ttu-id="7f589-274">Exibe a ajuda personalizada para a função de usuário especificada.</span><span class="sxs-lookup"><span data-stu-id="7f589-274">Displays help customized for the specified user role.</span></span> <span data-ttu-id="7f589-275">Insira uma função.</span><span class="sxs-lookup"><span data-stu-id="7f589-275">Enter a role.</span></span> <span data-ttu-id="7f589-276">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="7f589-276">Wildcard characters are permitted.</span></span>

<span data-ttu-id="7f589-277">Insira a função que o usuário desempenha em uma organização.</span><span class="sxs-lookup"><span data-stu-id="7f589-277">Enter the role that the user plays in an organization.</span></span> <span data-ttu-id="7f589-278">Alguns cmdlets exibem texto diferente em seus arquivos de ajuda com base no valor deste parâmetro.</span><span class="sxs-lookup"><span data-stu-id="7f589-278">Some cmdlets display different text in their help files based on the value of this parameter.</span></span> <span data-ttu-id="7f589-279">Este parâmetro não tem nenhum efeito na ajuda para os cmdlets principais.</span><span class="sxs-lookup"><span data-stu-id="7f589-279">This parameter has no effect on help for the core cmdlets.</span></span>

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

### <span data-ttu-id="7f589-280">-Janela de</span><span class="sxs-lookup"><span data-stu-id="7f589-280">-ShowWindow</span></span>

<span data-ttu-id="7f589-281">Exibe o tópico da ajuda em uma janela para facilitar a leitura.</span><span class="sxs-lookup"><span data-stu-id="7f589-281">Displays the help topic in a window for easier reading.</span></span> <span data-ttu-id="7f589-282">A janela inclui um recurso **Localizar** pesquisa e uma caixa **configurações** que permite definir opções para a exibição, incluindo opções para exibir apenas as seções selecionadas de um tópico da ajuda.</span><span class="sxs-lookup"><span data-stu-id="7f589-282">The window includes a **Find** search feature and a **Settings** box that lets you set options for the display, including options to display only selected sections of a help topic.</span></span>

<span data-ttu-id="7f589-283">O parâmetro de **janela** é compatível com os tópicos de ajuda para comandos (cmdlets, funções, comandos CIM, scripts) e conceitos **sobre** artigos.</span><span class="sxs-lookup"><span data-stu-id="7f589-283">The **ShowWindow** parameter supports help topics for commands (cmdlets, functions, CIM commands, scripts) and conceptual **About** articles.</span></span> <span data-ttu-id="7f589-284">Ele não fornece ajuda sobre o provedor .</span><span class="sxs-lookup"><span data-stu-id="7f589-284">It does not support provider help.</span></span>

<span data-ttu-id="7f589-285">Esse parâmetro foi reintroduzido no PowerShell 7,0.</span><span class="sxs-lookup"><span data-stu-id="7f589-285">This parameter was reintroduced in PowerShell 7.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ShowWindow
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7f589-286">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7f589-286">CommonParameters</span></span>

<span data-ttu-id="7f589-287">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7f589-287">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7f589-288">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7f589-288">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7f589-289">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="7f589-289">INPUTS</span></span>

### <span data-ttu-id="7f589-290">Nenhum</span><span class="sxs-lookup"><span data-stu-id="7f589-290">None</span></span>

<span data-ttu-id="7f589-291">Você não pode enviar objetos pelo pipeline para o `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="7f589-291">You can't send objects down the pipeline to `Get-Help`.</span></span>

## <span data-ttu-id="7f589-292">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="7f589-292">OUTPUTS</span></span>

### <span data-ttu-id="7f589-293">ExtendedCmdletHelpInfo</span><span class="sxs-lookup"><span data-stu-id="7f589-293">ExtendedCmdletHelpInfo</span></span>

<span data-ttu-id="7f589-294">Se você executar `Get-Help` em um comando que não tem um arquivo de ajuda, o `Get-Help` retornará um objeto **ExtendedCmdletHelpInfo** que representa a ajuda gerada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7f589-294">If you run `Get-Help` on a command that doesn't have a help file, `Get-Help` returns an **ExtendedCmdletHelpInfo** object that represents autogenerated help.</span></span>

### <span data-ttu-id="7f589-295">System.String</span><span class="sxs-lookup"><span data-stu-id="7f589-295">System.String</span></span>

<span data-ttu-id="7f589-296">Se você receber um artigo de ajuda conceitual, o `Get-Help` o retornará como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7f589-296">If you get a conceptual help article, `Get-Help` returns it as a string.</span></span>

### <span data-ttu-id="7f589-297">MamlCommandHelpInfo</span><span class="sxs-lookup"><span data-stu-id="7f589-297">MamlCommandHelpInfo</span></span>

<span data-ttu-id="7f589-298">Se você receber um comando que tem um arquivo de ajuda, `Get-Help` o retornará um objeto **MamlCommandHelpInfo** .</span><span class="sxs-lookup"><span data-stu-id="7f589-298">If you get a command that has a help file, `Get-Help` returns a **MamlCommandHelpInfo** object.</span></span>

## <span data-ttu-id="7f589-299">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="7f589-299">NOTES</span></span>

<span data-ttu-id="7f589-300">O PowerShell 3,0 não inclui arquivos de ajuda.</span><span class="sxs-lookup"><span data-stu-id="7f589-300">PowerShell 3.0 doesn't include help files.</span></span> <span data-ttu-id="7f589-301">Para baixar e instalar os arquivos de ajuda que o `Get-Help` lê, use o `Update-Help` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7f589-301">To download and install the help files that `Get-Help` reads, use the `Update-Help` cmdlet.</span></span> <span data-ttu-id="7f589-302">Você pode usar o `Update-Help` cmdlet para baixar e instalar arquivos de ajuda para os comandos principais que acompanham o PowerShell e para quaisquer módulos que você instalar.</span><span class="sxs-lookup"><span data-stu-id="7f589-302">You can use the `Update-Help` cmdlet to download and install help files for the core commands that come with PowerShell and for any modules that you install.</span></span> <span data-ttu-id="7f589-303">Ele também pode ser usado para atualizar os arquivos de ajuda, de modo que a ajuda em seu computador nunca fique desatualizada.</span><span class="sxs-lookup"><span data-stu-id="7f589-303">You can also use it to update the help files so that the help on your computer is never outdated.</span></span>

<span data-ttu-id="7f589-304">Você também pode ler os artigos de ajuda sobre os comandos que acompanham o PowerShell online, começando em [introdução com o Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="7f589-304">You can also read the help articles about the commands that come with PowerShell online starting at [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

<span data-ttu-id="7f589-305">`Get-Help` exibe a ajuda na localidade definida para o sistema operacional Windows ou no idioma de fallback para essa localidade.</span><span class="sxs-lookup"><span data-stu-id="7f589-305">`Get-Help` displays help in the locale set for the Windows operating system or in the fallback language for that locale.</span></span> <span data-ttu-id="7f589-306">Se você não tiver arquivos de ajuda para a localidade primária ou de fallback, o `Get-Help` se comporta como se não houvesse arquivos de ajuda no computador.</span><span class="sxs-lookup"><span data-stu-id="7f589-306">If you don't have help files for the primary or fallback locale, `Get-Help` behaves as if there are no help files on the computer.</span></span> <span data-ttu-id="7f589-307">Para obter ajuda para uma localidade diferente, use **região** e **idioma** no painel de controle para alterar as configurações.</span><span class="sxs-lookup"><span data-stu-id="7f589-307">To get help for a different locale, use **Region** and **Language** in Control Panel to change the settings.</span></span> <span data-ttu-id="7f589-308">No Windows 10, **configurações** , **hora & idioma** .</span><span class="sxs-lookup"><span data-stu-id="7f589-308">On Windows 10, **Settings** , **Time & Language** .</span></span>

<span data-ttu-id="7f589-309">A exibição completa da ajuda inclui uma tabela de informações sobre os parâmetros.</span><span class="sxs-lookup"><span data-stu-id="7f589-309">The full view of help includes a table of information about the parameters.</span></span> <span data-ttu-id="7f589-310">A tabela inclui os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="7f589-310">The table includes the following fields:</span></span>

- <span data-ttu-id="7f589-311">**Obrigatório** .</span><span class="sxs-lookup"><span data-stu-id="7f589-311">**Required** .</span></span> <span data-ttu-id="7f589-312">Indica se o parâmetro é obrigatório (verdadeiro) ou opcional (falso).</span><span class="sxs-lookup"><span data-stu-id="7f589-312">Indicates whether the parameter is required (true) or optional (false).</span></span>

- <span data-ttu-id="7f589-313">**Posição** .</span><span class="sxs-lookup"><span data-stu-id="7f589-313">**Position** .</span></span> <span data-ttu-id="7f589-314">Indica se o parâmetro é nomeado ou posicional (numérico).</span><span class="sxs-lookup"><span data-stu-id="7f589-314">Indicates whether the parameter is named or positional (numeric).</span></span> <span data-ttu-id="7f589-315">Parâmetros posicionais devem aparecer em um local especificado no comando.</span><span class="sxs-lookup"><span data-stu-id="7f589-315">Positional parameters must appear in a specified place in the command.</span></span>

- <span data-ttu-id="7f589-316">**Chamado** indica que o nome do parâmetro é necessário, mas que o parâmetro pode aparecer em qualquer lugar no comando.</span><span class="sxs-lookup"><span data-stu-id="7f589-316">**Named** indicates that the parameter name is required, but that the parameter can appear anywhere in the command.</span></span>

- <span data-ttu-id="7f589-317">**Numeric** indica que o nome do parâmetro é opcional, mas quando o nome é omitido, o parâmetro deve estar no local especificado pelo número.</span><span class="sxs-lookup"><span data-stu-id="7f589-317">**Numeric** indicates that the parameter name is optional, but when the name is omitted, the parameter must be in the place specified by the number.</span></span> <span data-ttu-id="7f589-318">Por exemplo, `2` indica que quando o nome do parâmetro é omitido, o parâmetro deve ser o segundo ou apenas o parâmetro não nomeado no comando.</span><span class="sxs-lookup"><span data-stu-id="7f589-318">For example, `2` indicates that when the parameter name is omitted, the parameter must be the second or only unnamed parameter in the command.</span></span> <span data-ttu-id="7f589-319">Quando o nome do parâmetro é usado, o parâmetro pode aparecer em qualquer lugar no comando.</span><span class="sxs-lookup"><span data-stu-id="7f589-319">When the parameter name is used, the parameter can appear anywhere in the command.</span></span>

- <span data-ttu-id="7f589-320">**Valor padrão** .</span><span class="sxs-lookup"><span data-stu-id="7f589-320">**Default value** .</span></span> <span data-ttu-id="7f589-321">O valor do parâmetro ou o comportamento padrão que o PowerShell usa se você não incluir o parâmetro no comando.</span><span class="sxs-lookup"><span data-stu-id="7f589-321">The parameter value or default behavior that PowerShell uses if you don't include the parameter in the command.</span></span>

- <span data-ttu-id="7f589-322">Aceita a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="7f589-322">Accepts pipeline input.</span></span> <span data-ttu-id="7f589-323">Indica se você pode (true) ou não pode (falso) enviar objetos para o parâmetro por meio de um pipeline.</span><span class="sxs-lookup"><span data-stu-id="7f589-323">Indicates whether you can (true) or can't (false) send objects to the parameter through a pipeline.</span></span> <span data-ttu-id="7f589-324">**Por nome de propriedade** significa que o objeto de pipeline deve ter uma propriedade que tenha o mesmo nome que o nome do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="7f589-324">**By Property Name** means that the pipelined object must have a property that has the same name as the parameter name.</span></span>

- <span data-ttu-id="7f589-325">**Aceita caracteres curinga** .</span><span class="sxs-lookup"><span data-stu-id="7f589-325">**Accepts wildcard characters** .</span></span> <span data-ttu-id="7f589-326">Indica se o valor de um parâmetro pode incluir caracteres curinga, como um asterisco ( `*` ) ou um ponto de interrogação ( `?` ).</span><span class="sxs-lookup"><span data-stu-id="7f589-326">Indicates whether the value of a parameter can include wildcard characters, such as an asterisk (`*`) or question mark (`?`).</span></span>

## <span data-ttu-id="7f589-327">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="7f589-327">RELATED LINKS</span></span>

[<span data-ttu-id="7f589-328">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="7f589-328">about_Command_Syntax</span></span>](About/about_Command_Syntax.md)

[<span data-ttu-id="7f589-329">about_Comment_Based_Help</span><span class="sxs-lookup"><span data-stu-id="7f589-329">about_Comment_Based_Help</span></span>](./About/about_Comment_Based_Help.md)

[<span data-ttu-id="7f589-330">Get-Command</span><span class="sxs-lookup"><span data-stu-id="7f589-330">Get-Command</span></span>](Get-Command.md)

[<span data-ttu-id="7f589-331">Suporte à ajuda atualizável</span><span class="sxs-lookup"><span data-stu-id="7f589-331">Supporting Updatable Help</span></span>](/powershell/scripting/developer/module/supporting-updatable-help)

[<span data-ttu-id="7f589-332">Update-Help</span><span class="sxs-lookup"><span data-stu-id="7f589-332">Update-Help</span></span>](Update-Help.md)

[<span data-ttu-id="7f589-333">Escrever tópicos da ajuda baseados em comentário</span><span class="sxs-lookup"><span data-stu-id="7f589-333">Writing Comment-Based Help Topics</span></span>](/powershell/scripting/developer/help/writing-comment-based-help-topics)

[<span data-ttu-id="7f589-334">Escrever tópicos de ajuda para cmdlets do PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f589-334">Writing Help for PowerShell Cmdlets</span></span>](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets)
