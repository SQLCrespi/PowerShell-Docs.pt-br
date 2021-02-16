---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-html?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Html
ms.openlocfilehash: 1eade078765f93713da1f665e3ad6f062a1826d9
ms.sourcegitcommit: 9777152e026c47ba8d319593051416054cb62246
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2021
ms.locfileid: "100529933"
---
# <span data-ttu-id="bcd92-103">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="bcd92-103">ConvertTo-Html</span></span>

## <span data-ttu-id="bcd92-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="bcd92-104">SYNOPSIS</span></span>
<span data-ttu-id="bcd92-105">Converte objetos .NET em HTML que pode ser exibido em um navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="bcd92-105">Converts .NET objects into HTML that can be displayed in a Web browser.</span></span>

## <span data-ttu-id="bcd92-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bcd92-106">SYNTAX</span></span>

### <span data-ttu-id="bcd92-107">Página (padrão)</span><span class="sxs-lookup"><span data-stu-id="bcd92-107">Page (Default)</span></span>

```
ConvertTo-Html [-InputObject <PSObject>] [[-Property] <Object[]>] [[-Body] <String[]>]
 [[-Head] <String[]>] [[-Title] <String>] [-As <String>] [-CssUri <Uri>] [-PostContent <String[]>]
 [-PreContent <String[]>] [-Meta <Hashtable>] [-Charset <String>] [-Transitional]
 [<CommonParameters>]
```

### <span data-ttu-id="bcd92-108">Fragmento</span><span class="sxs-lookup"><span data-stu-id="bcd92-108">Fragment</span></span>

```
ConvertTo-Html [-InputObject <PSObject>] [[-Property] <Object[]>] [-As <String>] [-Fragment]
 [-PostContent <String[]>] [-PreContent <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="bcd92-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bcd92-109">DESCRIPTION</span></span>

<span data-ttu-id="bcd92-110">O `ConvertTo-Html` cmdlet converte objetos .net em HTML que podem ser exibidos em um navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="bcd92-110">The `ConvertTo-Html` cmdlet converts .NET objects into HTML that can be displayed in a Web browser.</span></span> <span data-ttu-id="bcd92-111">Você pode usar este cmdlet para exibir a saída de um comando em uma página da Web.</span><span class="sxs-lookup"><span data-stu-id="bcd92-111">You can use this cmdlet to display the output of a command in a Web page.</span></span>

<span data-ttu-id="bcd92-112">Você pode usar os parâmetros de `ConvertTo-Html` para selecionar Propriedades de objeto, para especificar um formato de tabela ou lista, para especificar o título da página HTML, para adicionar texto antes e depois do objeto, e para retornar apenas a tabela ou fragmento de lista, em vez de uma página DTD estrita.</span><span class="sxs-lookup"><span data-stu-id="bcd92-112">You can use the parameters of `ConvertTo-Html` to select object properties, to specify a table or list format, to specify the HTML page title, to add text before and after the object, and to return only the table or list fragment, instead of a strict DTD page.</span></span>

<span data-ttu-id="bcd92-113">Quando você envia vários objetos para `ConvertTo-Html` o, o PowerShell cria a tabela (ou lista) com base nas propriedades do primeiro objeto que você enviar.</span><span class="sxs-lookup"><span data-stu-id="bcd92-113">When you submit multiple objects to `ConvertTo-Html`, PowerShell creates the table (or list) based on the properties of the first object that you submit.</span></span> <span data-ttu-id="bcd92-114">Se os objetos restantes não tiverem uma das propriedades especificadas, o valor da propriedade do objeto será uma célula vazia.</span><span class="sxs-lookup"><span data-stu-id="bcd92-114">If the remaining objects do not have one of the specified properties, the property value of that object is an empty cell.</span></span> <span data-ttu-id="bcd92-115">Se os objetos restantes têm propriedades adicionais, os valores de propriedade não são incluídos no arquivo.</span><span class="sxs-lookup"><span data-stu-id="bcd92-115">If the remaining objects have additional properties, those property values are not included in the file.</span></span>

## <span data-ttu-id="bcd92-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="bcd92-116">EXAMPLES</span></span>

### <span data-ttu-id="bcd92-117">Exemplo 1: criar uma página da Web para exibir a data</span><span class="sxs-lookup"><span data-stu-id="bcd92-117">Example 1: Create a web page to display the date</span></span>

```powershell
ConvertTo-Html -InputObject (Get-Date)
```

<span data-ttu-id="bcd92-118">Este comando cria uma página HTML que exibe as propriedades da data atual.</span><span class="sxs-lookup"><span data-stu-id="bcd92-118">This command creates an HTML page that displays the properties of the current date.</span></span> <span data-ttu-id="bcd92-119">Ele usa o parâmetro **InputObject** para enviar os resultados de um `Get-Date` comando para o `ConvertTo-Html` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bcd92-119">It uses the **InputObject** parameter to submit the results of a `Get-Date` command to the `ConvertTo-Html` cmdlet.</span></span>

### <span data-ttu-id="bcd92-120">Exemplo 2: criar uma página da Web para exibir aliases do PowerShell</span><span class="sxs-lookup"><span data-stu-id="bcd92-120">Example 2: Create a web page to display PowerShell aliases</span></span>

```powershell
Get-Alias | ConvertTo-Html | Out-File aliases.htm
Invoke-Item aliases.htm
```

<span data-ttu-id="bcd92-121">Este comando cria uma página HTML que lista os aliases do PowerShell no console atual.</span><span class="sxs-lookup"><span data-stu-id="bcd92-121">This command creates an HTML page that lists the PowerShell aliases in the current console.</span></span>

<span data-ttu-id="bcd92-122">O comando usa o `Get-Alias` cmdlet para obter os aliases.</span><span class="sxs-lookup"><span data-stu-id="bcd92-122">The command uses the `Get-Alias` cmdlet to get the aliases.</span></span> <span data-ttu-id="bcd92-123">Ele usa o operador de pipeline ( `|` ) para enviar os aliases para o `ConvertTo-Html` cmdlet, que cria a página HTML.</span><span class="sxs-lookup"><span data-stu-id="bcd92-123">It uses the pipeline operator (`|`) to send the aliases to the `ConvertTo-Html` cmdlet, which creates the HTML page.</span></span> <span data-ttu-id="bcd92-124">O comando também usa o `Out-File` cmdlet para enviar o código HTML para o `aliases.htm` arquivo.</span><span class="sxs-lookup"><span data-stu-id="bcd92-124">The command also uses the `Out-File` cmdlet to send the HTML code to the `aliases.htm` file.</span></span>

### <span data-ttu-id="bcd92-125">Exemplo 3: criar uma página da Web para exibir eventos do PowerShell</span><span class="sxs-lookup"><span data-stu-id="bcd92-125">Example 3: Create a web page to display PowerShell events</span></span>

```powershell
Get-EventLog -LogName "Windows PowerShell" | ConvertTo-Html | Out-File pslog.htm
```

<span data-ttu-id="bcd92-126">Este comando cria uma página HTML chamada `pslog.htm` que exibe os eventos no log de eventos do Windows PowerShell no computador local.</span><span class="sxs-lookup"><span data-stu-id="bcd92-126">This command creates an HTML page called `pslog.htm` that displays the events in the Windows PowerShell event log on the local computer.</span></span>

<span data-ttu-id="bcd92-127">Ele usa o `Get-EventLog` cmdlet para obter os eventos no log do Windows PowerShell e, em seguida, usa o operador de pipeline ( `|` ) para enviar os eventos para o `ConvertTo-Html` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bcd92-127">It uses the `Get-EventLog` cmdlet to get the events in the Windows PowerShell log and then uses the pipeline operator (`|`) to send the events to the `ConvertTo-Html` cmdlet.</span></span> <span data-ttu-id="bcd92-128">O comando também usa o `Out-File` cmdlet para enviar o código HTML para o `pslog.htm` arquivo.</span><span class="sxs-lookup"><span data-stu-id="bcd92-128">The command also uses the `Out-File` cmdlet to send the HTML code to the `pslog.htm` file.</span></span>

<span data-ttu-id="bcd92-129">O comando também usa o `Out-File` cmdlet para enviar o código HTML para o `pslog.htm` arquivo.</span><span class="sxs-lookup"><span data-stu-id="bcd92-129">The command also uses the `Out-File` cmdlet to send the HTML code to the `pslog.htm` file.</span></span>

### <span data-ttu-id="bcd92-130">Exemplo 4: criar uma página da Web para exibir processos</span><span class="sxs-lookup"><span data-stu-id="bcd92-130">Example 4: Create a web page to display processes</span></span>

```powershell
Get-Process |
  ConvertTo-Html -Property Name, Path, Company -Title "Process Information" |
    Out-File proc.htm
Invoke-Item proc.htm
```

<span data-ttu-id="bcd92-131">Esses comandos criam e abrem uma página HTML que lista o nome, o caminho e a empresa dos processos no computador local.</span><span class="sxs-lookup"><span data-stu-id="bcd92-131">These commands create and open an HTML page that lists the name, path, and company of the processes on the local computer.</span></span>

<span data-ttu-id="bcd92-132">O primeiro comando usa o `Get-Process` cmdlet para obter objetos que representam os processos em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="bcd92-132">The first command uses the `Get-Process` cmdlet to get objects that represent the processes running on the computer.</span></span> <span data-ttu-id="bcd92-133">O comando usa o operador de pipeline ( `|` ) para enviar os objetos de processo para o `ConvertTo-Html` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bcd92-133">The command uses the pipeline operator (`|`) to send the process objects to the `ConvertTo-Html` cmdlet.</span></span>

<span data-ttu-id="bcd92-134">O comando usa o parâmetro **Property** para selecionar três propriedades dos objetos de processo a serem incluídos na tabela.</span><span class="sxs-lookup"><span data-stu-id="bcd92-134">The command uses the **Property** parameter to select three properties of the process objects to be included in the table.</span></span> <span data-ttu-id="bcd92-135">O comando usa o parâmetro **title** para especificar um título para a página HTML.</span><span class="sxs-lookup"><span data-stu-id="bcd92-135">The command uses the **Title** parameter to specify a title for the HTML page.</span></span> <span data-ttu-id="bcd92-136">O comando também usa o `Out-File` cmdlet para enviar o HTML resultante para um arquivo chamado Proc.htm.</span><span class="sxs-lookup"><span data-stu-id="bcd92-136">The command also uses the `Out-File` cmdlet to send the resulting HTML to a file named Proc.htm.</span></span>

<span data-ttu-id="bcd92-137">O segundo comando usa o `Invoke-Item` cmdlet para abrir o `Proc.htm` no navegador padrão.</span><span class="sxs-lookup"><span data-stu-id="bcd92-137">The second command uses the `Invoke-Item` cmdlet to open the `Proc.htm` in the default browser.</span></span>

### <span data-ttu-id="bcd92-138">Exemplo 5: criar uma página da Web para exibir objetos de serviço</span><span class="sxs-lookup"><span data-stu-id="bcd92-138">Example 5: Create a web page to display service objects</span></span>

```powershell
Get-Service | ConvertTo-Html -CssUri "test.css"
```

```Output
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"  "https://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
<html>
<head>
<title>HTML TABLE</title>
<link rel="stylesheet" type="text/css" href="test.css" />
...
```

<span data-ttu-id="bcd92-139">Este comando cria uma página HTML dos objetos de serviço que o `Get-Service` cmdlet retorna.</span><span class="sxs-lookup"><span data-stu-id="bcd92-139">This command creates an HTML page of the service objects that the `Get-Service` cmdlet returns.</span></span> <span data-ttu-id="bcd92-140">O comando usa o parâmetro **CssUri** para especificar uma folha de estilos em cascata para a página HTML.</span><span class="sxs-lookup"><span data-stu-id="bcd92-140">The command uses the **CssUri** parameter to specify a cascading style sheet for the HTML page.</span></span>

<span data-ttu-id="bcd92-141">O parâmetro **CssUri** adiciona uma `<link rel="stylesheet" type="text/css" href="test.css">` marca adicional ao HTML resultante.</span><span class="sxs-lookup"><span data-stu-id="bcd92-141">The **CssUri** parameter adds an additional `<link rel="stylesheet" type="text/css" href="test.css">` tag to the resulting HTML.</span></span> <span data-ttu-id="bcd92-142">O atributo HREF na marca contém o nome da folha de estilos.</span><span class="sxs-lookup"><span data-stu-id="bcd92-142">The HREF attribute in the tag contains the name of the style sheet.</span></span>

### <span data-ttu-id="bcd92-143">Exemplo 6: criar uma página da Web para exibir objetos de serviço</span><span class="sxs-lookup"><span data-stu-id="bcd92-143">Example 6: Create a web page to display service objects</span></span>

```powershell
Get-Service | ConvertTo-Html -As LIST | Out-File services.htm
```

<span data-ttu-id="bcd92-144">Este comando cria uma página HTML dos objetos de serviço que o `Get-Service` cmdlet retorna.</span><span class="sxs-lookup"><span data-stu-id="bcd92-144">This command creates an HTML page of the service objects that the `Get-Service` cmdlet returns.</span></span> <span data-ttu-id="bcd92-145">O comando usa o **parâmetro as** para especificar um formato de lista.</span><span class="sxs-lookup"><span data-stu-id="bcd92-145">The command uses the **As** parameter to specify a list format.</span></span> <span data-ttu-id="bcd92-146">O cmdlet `Out-File` envia o HTML resultante para o `Services.htm` arquivo.</span><span class="sxs-lookup"><span data-stu-id="bcd92-146">The cmdlet `Out-File` sends the resulting HTML to the `Services.htm` file.</span></span>

### <span data-ttu-id="bcd92-147">Exemplo 7: criar uma tabela da Web para a data atual</span><span class="sxs-lookup"><span data-stu-id="bcd92-147">Example 7: Create a web table for the current date</span></span>

```powershell
Get-Date | ConvertTo-Html -Fragment
```

```Output
<table>
<colgroup>...</colgroup>
<tr><th>DisplayHint</th><th>DateTime</th><th>Date</th><th>Day</th><th>DayOfWeek</th><th>DayOfYear</th><th>Hour</th>
<th>Kind</th><th>Millisecond</th><th>Minute</th><th>Month</th><th>Second</th><th>Ticks</th><th>TimeOfDay</th><th>Year</th></tr>
<tr><td>DateTime</td><td>Monday, May 05, 2008 10:40:04 AM</td><td>5/5/2008 12:00:00 AM</td><td>5</td><td>Monday</td>
<td>126</td><td>10</td><td>Local</td><td>123</td><td>40</td><td>5</td><td>4</td><td>633455808041237213</td><td>10:40:04.12
37213</td><td>2008</td></tr>
</table>
```

<span data-ttu-id="bcd92-148">Esse comando usa `ConvertTo-Html` para gerar uma tabela HTML da data atual.</span><span class="sxs-lookup"><span data-stu-id="bcd92-148">This command uses `ConvertTo-Html` to generate an HTML table of the current date.</span></span> <span data-ttu-id="bcd92-149">O comando usa o `Get-Date` cmdlet para obter a data atual.</span><span class="sxs-lookup"><span data-stu-id="bcd92-149">The command uses the `Get-Date` cmdlet to get the current date.</span></span> <span data-ttu-id="bcd92-150">Ele usa um operador de pipeline (|) para enviar os resultados para o `ConvertTo-Html` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bcd92-150">It uses a pipeline operator (|) to send the results to the `ConvertTo-Html` cmdlet.</span></span>

<span data-ttu-id="bcd92-151">O `ConvertTo-Html` comando inclui o parâmetro **Fragment** , que limita a saída a uma tabela HTML.</span><span class="sxs-lookup"><span data-stu-id="bcd92-151">The `ConvertTo-Html` command includes the **Fragment** parameter, which limits the output to an HTML table.</span></span> <span data-ttu-id="bcd92-152">Como resultado, os outros elementos de uma página HTML, como as marcas `<HEAD>` e `<BODY>`, são omitidos.</span><span class="sxs-lookup"><span data-stu-id="bcd92-152">As a result, the other elements of an HTML page, such as the `<HEAD>` and `<BODY>` tags, are omitted.</span></span>

### <span data-ttu-id="bcd92-153">Exemplo 8: criar uma página da Web para exibir eventos do PowerShell</span><span class="sxs-lookup"><span data-stu-id="bcd92-153">Example 8: Create a web page to display PowerShell events</span></span>

```powershell
Get-EventLog -Log "Windows PowerShell" | ConvertTo-Html -Property id, level, task
```

<span data-ttu-id="bcd92-154">Esse comando usa o `Get-EventLog` cmdlet para obter eventos do log de eventos do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bcd92-154">This command uses the `Get-EventLog` cmdlet to get events from the Windows PowerShell event log.</span></span>

<span data-ttu-id="bcd92-155">Ele usa um operador de pipeline ( `|` ) para enviar os eventos para o `ConvertTo-Html` cmdlet, que converte os eventos em formato HTML.</span><span class="sxs-lookup"><span data-stu-id="bcd92-155">It uses a pipeline operator (`|`) to send the events to the `ConvertTo-Html` cmdlet, which converts the events to HTML format.</span></span>

<span data-ttu-id="bcd92-156">O `ConvertTo-Html` comando usa o parâmetro **Property** para selecionar apenas as propriedades **ID**, **Level** e **Task** do evento.</span><span class="sxs-lookup"><span data-stu-id="bcd92-156">The `ConvertTo-Html` command uses the **Property** parameter to select only the **ID**, **Level**, and **Task** properties of the event.</span></span>

### <span data-ttu-id="bcd92-157">Exemplo 9: criar uma página da Web para exibir os serviços especificados</span><span class="sxs-lookup"><span data-stu-id="bcd92-157">Example 9: Create a web page to display specified services</span></span>

```powershell
$htmlParams = @{
  Title = "Windows Services: Server01"
  Body = Get-Date
  PreContent = "<P>Generated by Corporate IT</P>"
  PostContent = "For details, contact Corporate IT."
}
Get-Service A* |
  ConvertTo-Html @htmlParams |
    Out-File Services.htm
Invoke-Item Services.htm
```

<span data-ttu-id="bcd92-158">Esse comando cria e abre uma página da Web que exibe os serviços no computador que começam com um. Ele usa os parâmetros **título**, **corpo**, **PreContent** e **anticontent** de `ConvertTo-Html` para personalizar a saída.</span><span class="sxs-lookup"><span data-stu-id="bcd92-158">This command creates and opens a Web page that displays the services on the computer that begin with A. It uses the **Title**, **Body**, **PreContent**, and **PostContent** parameters of `ConvertTo-Html` to customize the output.</span></span>

<span data-ttu-id="bcd92-159">A primeira parte do comando usa o `Get-Service` cmdlet para obter os serviços no computador que começam com um. O comando usa um operador de pipeline ( `|` ) para enviar os resultados para o `ConvertTo-Html` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bcd92-159">The first part of the command uses the `Get-Service` cmdlet to get the services on the computer that begin with A. The command uses a pipeline operator (`|`) to send the results to the `ConvertTo-Html` cmdlet.</span></span> <span data-ttu-id="bcd92-160">O comando também usa o `Out-File` cmdlet para enviar a saída para o arquivo de Services.htm.</span><span class="sxs-lookup"><span data-stu-id="bcd92-160">The command also uses the `Out-File` cmdlet to send the output to the Services.htm file.</span></span>

<span data-ttu-id="bcd92-161">Um ponto e vírgula ( `;` ) termina o primeiro comando e inicia um segundo comando, que usa o `Invoke-Item` cmdlet para abrir o `Services.htm` arquivo no navegador padrão.</span><span class="sxs-lookup"><span data-stu-id="bcd92-161">A semicolon (`;`) ends the first command and starts a second command, which uses the `Invoke-Item` cmdlet to open the `Services.htm` file in the default browser.</span></span>

### <span data-ttu-id="bcd92-162">Exemplo 10: definir as propriedades meta e o conjunto de caracteres do HTML</span><span class="sxs-lookup"><span data-stu-id="bcd92-162">Example 10: Set the Meta properties and Charset of the HTML</span></span>

```powershell
Get-Service | ConvertTo-HTML -Meta @{
  refresh=10
  author="Author's Name"
  keywords="PowerShell, HTML, ConvertTo-HTML"
} -Charset "UTF-8"
```

<span data-ttu-id="bcd92-163">Este comando cria o HTML para uma página da Web com as marcas meta para atualização, autor e palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="bcd92-163">This command creates the HTML for a webpage with the meta tags for refresh, author, and keywords.</span></span>
<span data-ttu-id="bcd92-164">O conjunto de caracteres da página está definido como UTF-8</span><span class="sxs-lookup"><span data-stu-id="bcd92-164">The charset for the page is set to UTF-8</span></span>

### <span data-ttu-id="bcd92-165">Exemplo 11: definir o HTML como DTD de transição XHTML</span><span class="sxs-lookup"><span data-stu-id="bcd92-165">Example 11: Set the HTML to XHTML Transitional DTD</span></span>

```powershell
Get-Service | ConvertTo-HTML -Transitional
```

<span data-ttu-id="bcd92-166">Este comando define o DOCTYPE do HTML retornado para o DTD de transição XHTML</span><span class="sxs-lookup"><span data-stu-id="bcd92-166">This command sets the DOCTYPE of the returned HTML to XHTML Transitional DTD</span></span>

## <span data-ttu-id="bcd92-167">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bcd92-167">PARAMETERS</span></span>

### <span data-ttu-id="bcd92-168">-Como</span><span class="sxs-lookup"><span data-stu-id="bcd92-168">-As</span></span>

<span data-ttu-id="bcd92-169">Determina se o objeto é formatado como uma tabela ou uma lista.</span><span class="sxs-lookup"><span data-stu-id="bcd92-169">Determines whether the object is formatted as a table or a list.</span></span> <span data-ttu-id="bcd92-170">Os valores válidos são **tabela** e **lista**.</span><span class="sxs-lookup"><span data-stu-id="bcd92-170">Valid values are **Table** and **List**.</span></span> <span data-ttu-id="bcd92-171">O valor padrão é **Table**.</span><span class="sxs-lookup"><span data-stu-id="bcd92-171">The default value is **Table**.</span></span>

<span data-ttu-id="bcd92-172">O valor da **tabela** gera uma tabela HTML que se assemelha ao formato de tabela do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bcd92-172">The **Table** value generates an HTML table that resembles the PowerShell table format.</span></span> <span data-ttu-id="bcd92-173">A linha de cabeçalho exibe os nomes de propriedade.</span><span class="sxs-lookup"><span data-stu-id="bcd92-173">The header row displays the property names.</span></span> <span data-ttu-id="bcd92-174">Cada linha da tabela representa um objeto e exibe os valores do objeto para cada propriedade.</span><span class="sxs-lookup"><span data-stu-id="bcd92-174">Each table row represents an object and displays the object's values for each property.</span></span>

<span data-ttu-id="bcd92-175">O valor da **lista** gera uma tabela HTML de duas colunas para cada objeto que se assemelha ao formato de lista do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bcd92-175">The **List** value generates a two-column HTML table for each object that resembles the PowerShell list format.</span></span> <span data-ttu-id="bcd92-176">A primeira coluna exibe o nome da propriedade.</span><span class="sxs-lookup"><span data-stu-id="bcd92-176">The first column displays the property name.</span></span> <span data-ttu-id="bcd92-177">A segunda coluna exibe o valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="bcd92-177">The second column displays the property value.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Table, List

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bcd92-178">-Corpo</span><span class="sxs-lookup"><span data-stu-id="bcd92-178">-Body</span></span>

<span data-ttu-id="bcd92-179">Especifica o texto a ser adicionado após a marca de abertura `<BODY>`.</span><span class="sxs-lookup"><span data-stu-id="bcd92-179">Specifies the text to add after the opening `<BODY>` tag.</span></span> <span data-ttu-id="bcd92-180">Por padrão, não há nenhum texto nessa posição.</span><span class="sxs-lookup"><span data-stu-id="bcd92-180">By default, there is no text in that position.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Page
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bcd92-181">-Conjunto de caracteres</span><span class="sxs-lookup"><span data-stu-id="bcd92-181">-Charset</span></span>

<span data-ttu-id="bcd92-182">Especifica o texto a ser adicionado à `<charset>` marca de abertura.</span><span class="sxs-lookup"><span data-stu-id="bcd92-182">Specifies text to add to the opening `<charset>` tag.</span></span> <span data-ttu-id="bcd92-183">Por padrão, não há nenhum texto nessa posição.</span><span class="sxs-lookup"><span data-stu-id="bcd92-183">By default, there is no text in that position.</span></span>

<span data-ttu-id="bcd92-184">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="bcd92-184">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: Page
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bcd92-185">-CssUri</span><span class="sxs-lookup"><span data-stu-id="bcd92-185">-CssUri</span></span>

<span data-ttu-id="bcd92-186">Especifica o Uniform Resource Identifier (URI) da folha de estilos em cascata (CSS) que é aplicada ao arquivo HTML.</span><span class="sxs-lookup"><span data-stu-id="bcd92-186">Specifies the Uniform Resource Identifier (URI) of the cascading style sheet (CSS) that is applied to the HTML file.</span></span> <span data-ttu-id="bcd92-187">O URI é incluído em um link de folha de estilos na saída.</span><span class="sxs-lookup"><span data-stu-id="bcd92-187">The URI is included in a style sheet link in the output.</span></span>

```yaml
Type: System.Uri
Parameter Sets: Page
Aliases: cu, uri

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bcd92-188">-Fragmento</span><span class="sxs-lookup"><span data-stu-id="bcd92-188">-Fragment</span></span>

<span data-ttu-id="bcd92-189">Gera apenas uma tabela de HTML.</span><span class="sxs-lookup"><span data-stu-id="bcd92-189">Generates only an HTML table.</span></span> <span data-ttu-id="bcd92-190">As marcas HTML, HEAD, TITLE e BODY são omitidas.</span><span class="sxs-lookup"><span data-stu-id="bcd92-190">The HTML, HEAD, TITLE, and BODY tags are omitted.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Fragment
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bcd92-191">-Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="bcd92-191">-Head</span></span>

<span data-ttu-id="bcd92-192">Especifica o conteúdo da marca `<HEAD>`.</span><span class="sxs-lookup"><span data-stu-id="bcd92-192">Specifies the content of the `<HEAD>` tag.</span></span> <span data-ttu-id="bcd92-193">O padrão é `<title\>HTML TABLE</title>`.</span><span class="sxs-lookup"><span data-stu-id="bcd92-193">The default is `<title\>HTML TABLE</title>`.</span></span> <span data-ttu-id="bcd92-194">Se você usar o parâmetro **Head** , o parâmetro **title** será ignorado.</span><span class="sxs-lookup"><span data-stu-id="bcd92-194">If you use the **Head** parameter, the **Title** parameter is ignored.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Page
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bcd92-195">-InputObject</span><span class="sxs-lookup"><span data-stu-id="bcd92-195">-InputObject</span></span>

<span data-ttu-id="bcd92-196">Especifica os objetos a serem representadas em HTML.</span><span class="sxs-lookup"><span data-stu-id="bcd92-196">Specifies the objects to be represented in HTML.</span></span> <span data-ttu-id="bcd92-197">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="bcd92-197">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="bcd92-198">Se você usar esse parâmetro para enviar vários objetos, como todos os serviços em um computador, `ConvertTo-Html` o criará uma tabela que exibe as propriedades de uma coleção ou de uma matriz de objetos.</span><span class="sxs-lookup"><span data-stu-id="bcd92-198">If you use this parameter to submit multiple objects, such as all of the services on a computer, `ConvertTo-Html` creates a table that displays the properties of a collection or of an array of objects.</span></span> <span data-ttu-id="bcd92-199">Para criar uma tabela de objetos individuais, use o operador de pipeline para canalizar os objetos `ConvertTo-Html` .</span><span class="sxs-lookup"><span data-stu-id="bcd92-199">To create a table of the individual objects, use the pipeline operator to pipe the objects to `ConvertTo-Html`.</span></span>

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

### <span data-ttu-id="bcd92-200">-Meta</span><span class="sxs-lookup"><span data-stu-id="bcd92-200">-Meta</span></span>

<span data-ttu-id="bcd92-201">Especifica o texto a ser adicionado à `<meta>` marca de abertura.</span><span class="sxs-lookup"><span data-stu-id="bcd92-201">Specifies text to add to the opening `<meta>` tag.</span></span> <span data-ttu-id="bcd92-202">Por padrão, não há nenhum texto nessa posição.</span><span class="sxs-lookup"><span data-stu-id="bcd92-202">By default, there is no text in that position.</span></span>

<span data-ttu-id="bcd92-203">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="bcd92-203">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: Page
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bcd92-204">-O conteúdo</span><span class="sxs-lookup"><span data-stu-id="bcd92-204">-PostContent</span></span>

<span data-ttu-id="bcd92-205">Especifica o texto a ser adicionado após a marca de fechamento `</TABLE>`.</span><span class="sxs-lookup"><span data-stu-id="bcd92-205">Specifies text to add after the closing `</TABLE>` tag.</span></span> <span data-ttu-id="bcd92-206">Por padrão, não há nenhum texto nessa posição.</span><span class="sxs-lookup"><span data-stu-id="bcd92-206">By default, there is no text in that position.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bcd92-207">-PreContent</span><span class="sxs-lookup"><span data-stu-id="bcd92-207">-PreContent</span></span>

<span data-ttu-id="bcd92-208">Especifica o texto a ser adicionado após a marca de abertura `<TABLE>`.</span><span class="sxs-lookup"><span data-stu-id="bcd92-208">Specifies text to add before the opening `<TABLE>` tag.</span></span> <span data-ttu-id="bcd92-209">Por padrão, não há nenhum texto nessa posição.</span><span class="sxs-lookup"><span data-stu-id="bcd92-209">By default, there is no text in that position.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bcd92-210">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="bcd92-210">-Property</span></span>

<span data-ttu-id="bcd92-211">Inclui as propriedades especificadas dos objetos no HTML.</span><span class="sxs-lookup"><span data-stu-id="bcd92-211">Includes the specified properties of the objects in the HTML.</span></span> <span data-ttu-id="bcd92-212">O valor do parâmetro **Property** pode ser uma nova propriedade calculada.</span><span class="sxs-lookup"><span data-stu-id="bcd92-212">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="bcd92-213">A propriedade calculada pode ser um bloco de script ou uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="bcd92-213">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="bcd92-214">Os pares de chave-valor válidos são:</span><span class="sxs-lookup"><span data-stu-id="bcd92-214">Valid key-value pairs are:</span></span>

- <span data-ttu-id="bcd92-215">Nome (ou rótulo) – `<string>` (adicionado no PowerShell 6. x)</span><span class="sxs-lookup"><span data-stu-id="bcd92-215">Name (or label) - `<string>` (added in PowerShell 6.x)</span></span>
- <span data-ttu-id="bcd92-216">Expressão- `<string>` ou `<script block>`</span><span class="sxs-lookup"><span data-stu-id="bcd92-216">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="bcd92-217">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="bcd92-217">FormatString - `<string>`</span></span>
- <span data-ttu-id="bcd92-218">Largura- `<int32>` -deve ser maior que `0`</span><span class="sxs-lookup"><span data-stu-id="bcd92-218">Width - `<int32>` - must be greater than `0`</span></span>
- <span data-ttu-id="bcd92-219">Alinhamento-o valor pode ser `Left` , `Center` ou `Right`</span><span class="sxs-lookup"><span data-stu-id="bcd92-219">Alignment - value can be `Left`, `Center`, or `Right`</span></span>

<span data-ttu-id="bcd92-220">Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="bcd92-220">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bcd92-221">-Title</span><span class="sxs-lookup"><span data-stu-id="bcd92-221">-Title</span></span>

<span data-ttu-id="bcd92-222">Especifica um título para o arquivo HTML, ou seja, o texto que aparece entre as marcas `<TITLE>`.</span><span class="sxs-lookup"><span data-stu-id="bcd92-222">Specifies a title for the HTML file, that is, the text that appears between the `<TITLE>` tags.</span></span>

```yaml
Type: System.String
Parameter Sets: Page
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bcd92-223">-Transicional</span><span class="sxs-lookup"><span data-stu-id="bcd92-223">-Transitional</span></span>

<span data-ttu-id="bcd92-224">Altera o **DOCTYPE** para **DTD de transição XHTML**, o **DOCTYPE** padrão é um **DTD estrito de XHTML**.</span><span class="sxs-lookup"><span data-stu-id="bcd92-224">Changes the **DOCTYPE** to **XHTML Transitional DTD**, Default **DOCTYPE** is **XHTML Strict DTD**.</span></span>

<span data-ttu-id="bcd92-225">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="bcd92-225">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Page
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bcd92-226">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bcd92-226">CommonParameters</span></span>

<span data-ttu-id="bcd92-227">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bcd92-227">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bcd92-228">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bcd92-228">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bcd92-229">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="bcd92-229">INPUTS</span></span>

### <span data-ttu-id="bcd92-230">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="bcd92-230">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="bcd92-231">Você pode canalizar qualquer objeto .NET para `ConvertTo-Html` .</span><span class="sxs-lookup"><span data-stu-id="bcd92-231">You can pipe any .NET object to `ConvertTo-Html`.</span></span>

## <span data-ttu-id="bcd92-232">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="bcd92-232">OUTPUTS</span></span>

### <span data-ttu-id="bcd92-233">Documento System. String ou System.Xml.Xml</span><span class="sxs-lookup"><span data-stu-id="bcd92-233">System.String or System.Xml.XmlDocument</span></span>

<span data-ttu-id="bcd92-234">`ConvertTo-Html` Retorna uma série de cadeias de caracteres que compõem um HTML válido.</span><span class="sxs-lookup"><span data-stu-id="bcd92-234">`ConvertTo-Html` returns series of strings that comprise valid HTML.</span></span>

## <span data-ttu-id="bcd92-235">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="bcd92-235">NOTES</span></span>

<span data-ttu-id="bcd92-236">Para usar esse cmdlet, redirecione um ou mais objetos para o cmdlet ou use o parâmetro **InputObject** para especificar o objeto.</span><span class="sxs-lookup"><span data-stu-id="bcd92-236">To use this cmdlet, pipe one or more objects to the cmdlet or use the **InputObject** parameter to specify the object.</span></span> <span data-ttu-id="bcd92-237">Quando a entrada consiste em vários objetos, a saída desses dois métodos é bastante diferente.</span><span class="sxs-lookup"><span data-stu-id="bcd92-237">When the input consists of multiple objects, the output of these two methods is quite different.</span></span>

- <span data-ttu-id="bcd92-238">Quando você canaliza vários objetos para um cmdlet, o PowerShell envia os objetos para o cmdlet um de cada vez.</span><span class="sxs-lookup"><span data-stu-id="bcd92-238">When you pipe multiple objects to a cmdlet, PowerShell sends the objects to the cmdlet one at a time.</span></span> <span data-ttu-id="bcd92-239">Como resultado, `ConvertTo-Html` o cria uma tabela que exibe os objetos individuais.</span><span class="sxs-lookup"><span data-stu-id="bcd92-239">As a result, `ConvertTo-Html` creates a table that displays the individual objects.</span></span> <span data-ttu-id="bcd92-240">Por exemplo, se você canalizar os processos em um computador para `ConvertTo-Html` , a tabela resultante exibirá todos os processos.</span><span class="sxs-lookup"><span data-stu-id="bcd92-240">For example, if you pipe the processes on a computer to `ConvertTo-Html`, the resulting table displays all of the processes.</span></span>

- <span data-ttu-id="bcd92-241">Quando você usa o parâmetro **InputObject** para enviar vários objetos, `ConvertTo-Html` o recebe esses objetos como uma coleção ou como uma matriz.</span><span class="sxs-lookup"><span data-stu-id="bcd92-241">When you use the **InputObject** parameter to submit multiple objects, `ConvertTo-Html` receives these objects as a collection or as an array.</span></span> <span data-ttu-id="bcd92-242">Como resultado, ele cria uma tabela que exibe a matriz e suas propriedades, não os itens na matriz.</span><span class="sxs-lookup"><span data-stu-id="bcd92-242">As a result, it creates a table that displays the array and its properties, not the items in the array.</span></span> <span data-ttu-id="bcd92-243">Por exemplo, se você usar **InputObject** para enviar os processos em um computador para `ConvertTo-Html` , a tabela resultante exibirá uma matriz de objetos e suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="bcd92-243">For example, if you use **InputObject** to submit the processes on a computer to `ConvertTo-Html`, the resulting table displays an object array and its properties.</span></span>

  <span data-ttu-id="bcd92-244">Para obedecer ao DTD estrito de XHTML, a marca DOCTYPE é modificada de acordo:</span><span class="sxs-lookup"><span data-stu-id="bcd92-244">To comply with the XHTML Strict DTD, the DOCTYPE tag is modified accordingly:</span></span>

   `<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"   "https://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd"\>`

## <span data-ttu-id="bcd92-245">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="bcd92-245">RELATED LINKS</span></span>

[<span data-ttu-id="bcd92-246">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="bcd92-246">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="bcd92-247">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="bcd92-247">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="bcd92-248">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="bcd92-248">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="bcd92-249">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="bcd92-249">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)

[<span data-ttu-id="bcd92-250">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="bcd92-250">Export-Clixml</span></span>](Export-Clixml.md)

[<span data-ttu-id="bcd92-251">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="bcd92-251">Import-Clixml</span></span>](Import-Clixml.md)
