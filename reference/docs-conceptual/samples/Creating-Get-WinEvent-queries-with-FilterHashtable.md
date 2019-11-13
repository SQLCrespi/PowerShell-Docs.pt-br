---
ms.date: 09/13/2019
title: Criando consultas Get-WinEvent com FilterHashtable
ms.openlocfilehash: 35d18dc894d90e698b38395b79ff4cf395515909
ms.sourcegitcommit: 36e4c79afda2ce11febd93951e143687245f0b50
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/02/2019
ms.locfileid: "73444384"
---
# <a name="creating-get-winevent-queries-with-filterhashtable"></a><span data-ttu-id="cd8e7-102">Criando consultas Get-WinEvent com FilterHashtable</span><span class="sxs-lookup"><span data-stu-id="cd8e7-102">Creating Get-WinEvent queries with FilterHashtable</span></span>

<span data-ttu-id="cd8e7-103">Para ler a postagem de blog original do **Scripting Guy** de 3 de junho de 2014, confira [Use o FilterHashTable para filtrar log de eventos com o PowerShell](https://devblogs.microsoft.com/scripting/use-filterhashtable-to-filter-event-log-with-powershell/).</span><span class="sxs-lookup"><span data-stu-id="cd8e7-103">To read the original June 3, 2014 **Scripting Guy** blog post, see [Use FilterHashTable to Filter Event Log with PowerShell](https://devblogs.microsoft.com/scripting/use-filterhashtable-to-filter-event-log-with-powershell/).</span></span>

<span data-ttu-id="cd8e7-104">Este artigo é um trecho da postagem do blog original e explica como usar o parâmetro **FilterHashtable** do cmdlet `Get-WinEvent` para filtrar logs de eventos.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-104">This article is an excerpt of the original blog post and explains how to use the `Get-WinEvent` cmdlet's **FilterHashtable** parameter to filter event logs.</span></span> <span data-ttu-id="cd8e7-105">O cmdlet `Get-WinEvent` do PowerShell é um método poderoso de filtragem de logs de eventos e diagnósticos do Windows.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-105">PowerShell's `Get-WinEvent` cmdlet is a powerful method to filter Windows event and diagnostic logs.</span></span> <span data-ttu-id="cd8e7-106">Quando uma consulta `Get-WinEvent` usa o parâmetro **FilterHashtable**, seu desempenho é aprimorado.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-106">Performance improves when a `Get-WinEvent` query uses the **FilterHashtable** parameter.</span></span>

<span data-ttu-id="cd8e7-107">Quando você trabalha com grandes logs de eventos, não é eficiente enviar objetos pelo pipeline para um comando `Where-Object`.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-107">When you work with large event logs, it's not efficient to send objects down the pipeline to a `Where-Object` command.</span></span> <span data-ttu-id="cd8e7-108">Antes do PowerShell 6, o cmdlet `Get-EventLog` era outra opção para obter dados de log.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-108">Prior to PowerShell 6, the `Get-EventLog` cmdlet was another option to get log data.</span></span> <span data-ttu-id="cd8e7-109">Por exemplo, os comandos a seguir são ineficientes para filtrar os logs **Microsoft-Windows-Defrag**:</span><span class="sxs-lookup"><span data-stu-id="cd8e7-109">For example, the following commands are inefficient to filter the **Microsoft-Windows-Defrag** logs:</span></span>

```powershell
Get-EventLog -LogName Application | Where-Object Source -Match defrag

Get-WinEvent -LogName Application | Where-Object { $_.ProviderName -Match 'defrag' }
```

<span data-ttu-id="cd8e7-110">O comando a seguir usa uma tabela de hash que melhora o desempenho:</span><span class="sxs-lookup"><span data-stu-id="cd8e7-110">The following command uses a hash table that improves the performance:</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='*defrag'
}
```

## <a name="blog-posts-about-enumeration"></a><span data-ttu-id="cd8e7-111">Postagens no blog sobre enumeração</span><span class="sxs-lookup"><span data-stu-id="cd8e7-111">Blog posts about enumeration</span></span>

<span data-ttu-id="cd8e7-112">Este artigo apresenta informações sobre como usar os valores enumerados em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-112">This article presents information about how to use enumerated values in a hash table.</span></span> <span data-ttu-id="cd8e7-113">Para obter mais informações sobre a enumeração, leia as postagens de blog de **Scripting Guy**.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-113">For more information about enumeration, read these **Scripting Guy** blog posts.</span></span> <span data-ttu-id="cd8e7-114">Para criar uma função que retorne valores enumerados, confira [Enumerações e valores](https://devblogs.microsoft.com/scripting/hey-scripting-guy-weekend-scripter-enumerations-and-values).</span><span class="sxs-lookup"><span data-stu-id="cd8e7-114">To create a function that returns the enumerated values, see [Enumerations and Values](https://devblogs.microsoft.com/scripting/hey-scripting-guy-weekend-scripter-enumerations-and-values).</span></span>
<span data-ttu-id="cd8e7-115">Para obter mais informações, confira [a série de postagens de blog sobre enumeração de Scripting Guy](https://devblogs.microsoft.com/scripting/?s=about+enumeration).</span><span class="sxs-lookup"><span data-stu-id="cd8e7-115">For more information, see the [Scripting Guy series of blog posts about enumeration](https://devblogs.microsoft.com/scripting/?s=about+enumeration).</span></span>

## <a name="hash-table-key-value-pairs"></a><span data-ttu-id="cd8e7-116">Pares chave-valor da tabela de hash</span><span class="sxs-lookup"><span data-stu-id="cd8e7-116">Hash table key-value pairs</span></span>

<span data-ttu-id="cd8e7-117">Para criar consultas eficientes, use o cmdlet `Get-WinEvent` com o parâmetro **FilterHashtable**.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-117">To build efficient queries, use the `Get-WinEvent` cmdlet with the **FilterHashtable** parameter.</span></span>
<span data-ttu-id="cd8e7-118">O **FilterHashtable** aceita uma tabela de hash como filtro para obter informações específicas de logs de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-118">**FilterHashtable** accepts a hash table as a filter to get specific information from Windows event logs.</span></span> <span data-ttu-id="cd8e7-119">Uma tabela de hash usa pares **chave-valor**.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-119">A hash table uses **key-value** pairs.</span></span> <span data-ttu-id="cd8e7-120">Para obter informações sobre tabelas de hash, confira [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span><span class="sxs-lookup"><span data-stu-id="cd8e7-120">For more information about hash tables, see [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span></span>

<span data-ttu-id="cd8e7-121">Se os pares **chave-valor** estiverem na mesma linha, eles deverão ser separados por um ponto e vírgula.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-121">If the **key-value** pairs are on the same line, they must be separated by a semicolon.</span></span> <span data-ttu-id="cd8e7-122">Se cada par **chave-valor** estiver em uma linha separada, o ponto e vírgula não será necessário.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-122">If each **key-value** pair is on a separate line, the semicolon isn't needed.</span></span> <span data-ttu-id="cd8e7-123">Por exemplo, este artigo coloca pares **chave-valor** em linhas separadas e não usa ponto e vírgula.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-123">For example, this article places **key-value** pairs on separate lines and doesn't use semicolons.</span></span>

<span data-ttu-id="cd8e7-124">Este exemplo usa vários parâmetros **FilterHashtable** dos pares **chave-valor**.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-124">This sample uses several of the **FilterHashtable** parameter's **key-value** pairs.</span></span> <span data-ttu-id="cd8e7-125">A consulta completa inclui **LogName**, **ProviderName**, **Palavras-chave**, **ID** e **Nível**.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-125">The completed query includes **LogName**, **ProviderName**, **Keywords**, **ID**, and **Level**.</span></span>

<span data-ttu-id="cd8e7-126">Os pares **chave-valor** aceitos são mostrados na tabela a seguir e incluídos na documentação do parâmetro [Get-WinEvent](/powershell/module/microsoft.powershell.diagnostics/Get-WinEvent)
**FilterHashtable**.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-126">The accepted **key-value** pairs are shown in the following table and are included in the documentation for the [Get-WinEvent](/powershell/module/microsoft.powershell.diagnostics/Get-WinEvent)
**FilterHashtable** parameter.</span></span>

<span data-ttu-id="cd8e7-127">A tabela a seguir exibe os nomes de chave, os tipos de dados e se os caracteres curinga são aceitos para um valor de dados.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-127">The following table displays the key names, data types, and whether wildcard characters are accepted for a data value.</span></span>

|    <span data-ttu-id="cd8e7-128">Nome da chave</span><span class="sxs-lookup"><span data-stu-id="cd8e7-128">Key name</span></span>    | <span data-ttu-id="cd8e7-129">Tipo de dados de valor</span><span class="sxs-lookup"><span data-stu-id="cd8e7-129">Value data type</span></span> | <span data-ttu-id="cd8e7-130">Aceita caracteres curinga?</span><span class="sxs-lookup"><span data-stu-id="cd8e7-130">Accepts wildcard characters?</span></span> |
| -------------- | --------------- | ---------------------------- |
| <span data-ttu-id="cd8e7-131">LogName</span><span class="sxs-lookup"><span data-stu-id="cd8e7-131">LogName</span></span>        | `<String[]>`    | <span data-ttu-id="cd8e7-132">Sim</span><span class="sxs-lookup"><span data-stu-id="cd8e7-132">Yes</span></span>                          |
| <span data-ttu-id="cd8e7-133">ProviderName</span><span class="sxs-lookup"><span data-stu-id="cd8e7-133">ProviderName</span></span>   | `<String[]>`    | <span data-ttu-id="cd8e7-134">Sim</span><span class="sxs-lookup"><span data-stu-id="cd8e7-134">Yes</span></span>                          |
| <span data-ttu-id="cd8e7-135">Caminho</span><span class="sxs-lookup"><span data-stu-id="cd8e7-135">Path</span></span>           | `<String[]>`    | <span data-ttu-id="cd8e7-136">Não</span><span class="sxs-lookup"><span data-stu-id="cd8e7-136">No</span></span>                           |
| <span data-ttu-id="cd8e7-137">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="cd8e7-137">Keywords</span></span>       | `<Long[]>`      | <span data-ttu-id="cd8e7-138">Não</span><span class="sxs-lookup"><span data-stu-id="cd8e7-138">No</span></span>                           |
| <span data-ttu-id="cd8e7-139">ID</span><span class="sxs-lookup"><span data-stu-id="cd8e7-139">ID</span></span>             | `<Int32[]>`     | <span data-ttu-id="cd8e7-140">Não</span><span class="sxs-lookup"><span data-stu-id="cd8e7-140">No</span></span>                           |
| <span data-ttu-id="cd8e7-141">Nível</span><span class="sxs-lookup"><span data-stu-id="cd8e7-141">Level</span></span>          | `<Int32[]>`     | <span data-ttu-id="cd8e7-142">Não</span><span class="sxs-lookup"><span data-stu-id="cd8e7-142">No</span></span>                           |
| <span data-ttu-id="cd8e7-143">StartTime</span><span class="sxs-lookup"><span data-stu-id="cd8e7-143">StartTime</span></span>      | `<DateTime>`    | <span data-ttu-id="cd8e7-144">Não</span><span class="sxs-lookup"><span data-stu-id="cd8e7-144">No</span></span>                           |
| <span data-ttu-id="cd8e7-145">EndTime</span><span class="sxs-lookup"><span data-stu-id="cd8e7-145">EndTime</span></span>        | `<DateTime>`    | <span data-ttu-id="cd8e7-146">Não</span><span class="sxs-lookup"><span data-stu-id="cd8e7-146">No</span></span>                           |
| <span data-ttu-id="cd8e7-147">UserID</span><span class="sxs-lookup"><span data-stu-id="cd8e7-147">UserID</span></span>         | `<SID>`         | <span data-ttu-id="cd8e7-148">Não</span><span class="sxs-lookup"><span data-stu-id="cd8e7-148">No</span></span>                           |
| <span data-ttu-id="cd8e7-149">Dados</span><span class="sxs-lookup"><span data-stu-id="cd8e7-149">Data</span></span>           | `<String[]>`    | <span data-ttu-id="cd8e7-150">Não</span><span class="sxs-lookup"><span data-stu-id="cd8e7-150">No</span></span>                           |
| `<named-data>` | `<String[]>`    | <span data-ttu-id="cd8e7-151">Não</span><span class="sxs-lookup"><span data-stu-id="cd8e7-151">No</span></span>                           |

<span data-ttu-id="cd8e7-152">A chave `<named-data>` representa um campo de dados de evento nomeado.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-152">The `<named-data>` key represents a named event data field.</span></span> <span data-ttu-id="cd8e7-153">Por exemplo, o evento 1008 do Perflib pode conter os seguintes dados de evento:</span><span class="sxs-lookup"><span data-stu-id="cd8e7-153">For example, the Perflib event 1008 can contain the following event data:</span></span>

```xml
<EventData>
  <Data Name="Service">BITS</Data>
  <Data Name="Library">C:\Windows\System32\bitsperf.dll</Data>
  <Data Name="Win32Error">2</Data>
</EventData>
```

<span data-ttu-id="cd8e7-154">Você pode consultar esses eventos usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="cd8e7-154">You can query for these events using the following command:</span></span>

```powershell
Get-WinEvent -FilterHashtable @{LogName='Application'; 'Service'='Bits'}
```

> [!NOTE]
> <span data-ttu-id="cd8e7-155">A capacidade de consultar `<named-data>` foi adicionada no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-155">The ability to query for `<named-data>` was added in PowerShell 6.</span></span>

## <a name="building-a-query-with-a-hash-table"></a><span data-ttu-id="cd8e7-156">Como criar uma consulta com uma tabela de hash</span><span class="sxs-lookup"><span data-stu-id="cd8e7-156">Building a query with a hash table</span></span>

<span data-ttu-id="cd8e7-157">Para verificar os resultados e solucionar problemas, convém criar a tabela de hash com um par **chave-valor** de cada vez.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-157">To verify results and troubleshoot problems, it helps to build the hash table one **key-value** pair at a time.</span></span> <span data-ttu-id="cd8e7-158">A consulta obtém dados de log do **Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-158">The query gets data from the **Application** log.</span></span> <span data-ttu-id="cd8e7-159">A tabela de hash é equivalente a `Get-WinEvent –LogName Application`.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-159">The hash table is equivalent to `Get-WinEvent –LogName Application`.</span></span>

<span data-ttu-id="cd8e7-160">Para começar, crie uma consulta `Get-WinEvent`.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-160">To begin, create the `Get-WinEvent` query.</span></span> <span data-ttu-id="cd8e7-161">Use o par **chave-valor** do parâmetro **FilterHashtable** com a chave **LogName** e o valor **Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-161">Use the **FilterHashtable** parameter's **key-value** pair with the key, **LogName**, and the value, **Application**.</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
}
```

<span data-ttu-id="cd8e7-162">Continue a criar a tabela de hash com a chave **ProviderName**.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-162">Continue to build the hash table with the **ProviderName** key.</span></span> <span data-ttu-id="cd8e7-163">O **ProviderName** é o nome exibido no campo **Fonte** no **Visualizador de Eventos do Windows**.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-163">The **ProviderName** is the name that appears in the **Source** field in the **Windows Event Viewer**.</span></span> <span data-ttu-id="cd8e7-164">Por exemplo, **Runtime do .NET** na captura de tela a seguir:</span><span class="sxs-lookup"><span data-stu-id="cd8e7-164">For example, **.NET Runtime** in the following screenshot:</span></span>

![Imagem das fontes do Visualizador de Eventos do Windows.](./media/creating-get-winEvent-queries-with-filterhashtable/providername.png)

<span data-ttu-id="cd8e7-166">Atualize a tabela de hash e inclua o par **chave-valor** com a chave \*\*ProviderName e o valor **Tempo de execução do .NET**.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-166">Update the hash table and include the **key-value** pair with the key, \*\*ProviderName, and the value, **.NET Runtime**.</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
}
```

<span data-ttu-id="cd8e7-167">Se sua consulta precisar obter dados de logs de eventos arquivados, use a chave **Caminho**.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-167">If your query needs to get data from archived event logs, use the **Path** key.</span></span> <span data-ttu-id="cd8e7-168">O valor **Caminho** especifica o caminho completo para o arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-168">The **Path** value specifies the full path to the log file.</span></span> <span data-ttu-id="cd8e7-169">Para obter mais informações, confira a postagem no blog do **Scripting Guy**, [Use o PowerShell para analisar erros de log de eventos salvos](https://devblogs.microsoft.com/scripting/use-powershell-to-parse-saved-event-logs-for-errors).</span><span class="sxs-lookup"><span data-stu-id="cd8e7-169">For more information, see the **Scripting Guy** blog post, [Use PowerShell to Parse Saved Event Logs for Errors](https://devblogs.microsoft.com/scripting/use-powershell-to-parse-saved-event-logs-for-errors).</span></span>

## <a name="using-enumerated-values-in-a-hash-table"></a><span data-ttu-id="cd8e7-170">Usando valores enumerados em uma tabela de hash</span><span class="sxs-lookup"><span data-stu-id="cd8e7-170">Using enumerated values in a hash table</span></span>

<span data-ttu-id="cd8e7-171">A chave **Palavras-chave** é a próxima na tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-171">**Keywords** is the next key in the hash table.</span></span> <span data-ttu-id="cd8e7-172">O tipo de dados **Palavras-chave** é uma matriz do tipo de valor `[long]` que contém um número grande.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-172">The **Keywords** data type is an array of the `[long]` value type that holds a large number.</span></span> <span data-ttu-id="cd8e7-173">Use o seguinte comando para encontrar o valor máximo de `[long]`:</span><span class="sxs-lookup"><span data-stu-id="cd8e7-173">Use the following command to find the maximum value of `[long]`:</span></span>

```powershell
[long]::MaxValue
```

```Output
9223372036854775807
```

<span data-ttu-id="cd8e7-174">Para a chave **Palavras-chave**, o PowerShell usa um número, não uma cadeia de caracteres, como **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-174">For the **Keywords** key, PowerShell uses a number, not a string such as **Security**.</span></span> <span data-ttu-id="cd8e7-175">Embora sejam valores enumerados, o **Visualizador de Eventos do Windows** exibe as **Palavras-chave** como cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-175">**Windows Event Viewer** displays the **Keywords** as strings, but they are enumerated values.</span></span> <span data-ttu-id="cd8e7-176">Na tabela de hash, se você usar a chave **Palavras-chave** com um valor de cadeia de caracteres, será exibida uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-176">In the hash table, if you use the **Keywords** key with a string value, an error message is displayed.</span></span>

<span data-ttu-id="cd8e7-177">Abra o **Visualizador de Eventos do Windows** e, no painel **Ações**, clique em **Filtrar o registro atual**.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-177">Open the **Windows Event Viewer** and from the **Actions** pane, click on **Filter current log**.</span></span>
<span data-ttu-id="cd8e7-178">O menu suspenso **Palavras-chave** exibe as palavras-chave disponíveis, conforme mostrado na captura de tela a seguir:</span><span class="sxs-lookup"><span data-stu-id="cd8e7-178">The **Keywords** drop-down menu displays the available keywords, as shown in the following screenshot:</span></span>

![Imagem de palavras-chave do Visualizador de Eventos do Windows.](./media/creating-get-winEvent-queries-with-filterhashtable/keywords.png)

<span data-ttu-id="cd8e7-180">Use o seguinte comando para exibir os nomes das propriedades `StandardEventKeywords`.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-180">Use the following command to display the `StandardEventKeywords` property names.</span></span>

```powershell
[System.Diagnostics.Eventing.Reader.StandardEventKeywords] | Get-Member -Static -MemberType Property
```

```Output
   TypeName: System.Diagnostics.Eventing.Reader.StandardEventKeywords
Name             MemberType Definition
—-             ———- ———-
AuditFailure     Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
AuditSuccess     Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
CorrelationHint  Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
CorrelationHint2 Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
EventLogClassic  Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
None             Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
ResponseTime     Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
Sqm              Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
WdiContext       Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
WdiDiagnostic    Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
```

<span data-ttu-id="cd8e7-181">Os valores enumerados estão documentados no **.NET Framework**.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-181">The enumerated values are documented in the **.NET Framework**.</span></span> <span data-ttu-id="cd8e7-182">Para obter mais informações, confira [Enumeração StandardEventKeywords](/dotnet/api/system.diagnostics.eventing.reader.standardeventkeywords?redirectedfrom=MSDN&view=netframework-4.7.2).</span><span class="sxs-lookup"><span data-stu-id="cd8e7-182">For more information, see [StandardEventKeywords Enumeration](/dotnet/api/system.diagnostics.eventing.reader.standardeventkeywords?redirectedfrom=MSDN&view=netframework-4.7.2).</span></span>

<span data-ttu-id="cd8e7-183">Os nomes e valores enumerados das **Palavras-chave** são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="cd8e7-183">The **Keywords** names and enumerated values are as follows:</span></span>

| <span data-ttu-id="cd8e7-184">Nome</span><span class="sxs-lookup"><span data-stu-id="cd8e7-184">Name</span></span>             |  <span data-ttu-id="cd8e7-185">Valor</span><span class="sxs-lookup"><span data-stu-id="cd8e7-185">Value</span></span>            |
| ---------------- | ------------------|
| <span data-ttu-id="cd8e7-186">AuditFailure</span><span class="sxs-lookup"><span data-stu-id="cd8e7-186">AuditFailure</span></span>     | <span data-ttu-id="cd8e7-187">4503599627370496</span><span class="sxs-lookup"><span data-stu-id="cd8e7-187">4503599627370496</span></span>  |
| <span data-ttu-id="cd8e7-188">AuditSuccess</span><span class="sxs-lookup"><span data-stu-id="cd8e7-188">AuditSuccess</span></span>     | <span data-ttu-id="cd8e7-189">9007199254740992</span><span class="sxs-lookup"><span data-stu-id="cd8e7-189">9007199254740992</span></span>  |
| <span data-ttu-id="cd8e7-190">CorrelationHint2</span><span class="sxs-lookup"><span data-stu-id="cd8e7-190">CorrelationHint2</span></span> | <span data-ttu-id="cd8e7-191">18014398509481984</span><span class="sxs-lookup"><span data-stu-id="cd8e7-191">18014398509481984</span></span> |
| <span data-ttu-id="cd8e7-192">EventLogClassic</span><span class="sxs-lookup"><span data-stu-id="cd8e7-192">EventLogClassic</span></span>  | <span data-ttu-id="cd8e7-193">36028797018963968</span><span class="sxs-lookup"><span data-stu-id="cd8e7-193">36028797018963968</span></span> |
| <span data-ttu-id="cd8e7-194">Sqm</span><span class="sxs-lookup"><span data-stu-id="cd8e7-194">Sqm</span></span>              | <span data-ttu-id="cd8e7-195">2251799813685248</span><span class="sxs-lookup"><span data-stu-id="cd8e7-195">2251799813685248</span></span>  |
| <span data-ttu-id="cd8e7-196">WdiDiagnostic</span><span class="sxs-lookup"><span data-stu-id="cd8e7-196">WdiDiagnostic</span></span>    | <span data-ttu-id="cd8e7-197">1125899906842624</span><span class="sxs-lookup"><span data-stu-id="cd8e7-197">1125899906842624</span></span>  |
| <span data-ttu-id="cd8e7-198">WdiContext</span><span class="sxs-lookup"><span data-stu-id="cd8e7-198">WdiContext</span></span>       | <span data-ttu-id="cd8e7-199">562949953421312</span><span class="sxs-lookup"><span data-stu-id="cd8e7-199">562949953421312</span></span>   |
| <span data-ttu-id="cd8e7-200">ResponseTime</span><span class="sxs-lookup"><span data-stu-id="cd8e7-200">ResponseTime</span></span>     | <span data-ttu-id="cd8e7-201">281474976710656</span><span class="sxs-lookup"><span data-stu-id="cd8e7-201">281474976710656</span></span>   |
| <span data-ttu-id="cd8e7-202">Não</span><span class="sxs-lookup"><span data-stu-id="cd8e7-202">None</span></span>             | <span data-ttu-id="cd8e7-203">0</span><span class="sxs-lookup"><span data-stu-id="cd8e7-203">0</span></span>                 |

<span data-ttu-id="cd8e7-204">Atualize a tabela de hash e inclua o par **chave-valor** com a chave **Palavras-chave** e o valor de enumeração **EventLogClassic**, **36028797018963968**.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-204">Update the hash table and include the **key-value** pair with the key, **Keywords**, and the **EventLogClassic** enumeration value, **36028797018963968**.</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=36028797018963968
}
```

### <a name="keywords-static-property-value-optional"></a><span data-ttu-id="cd8e7-205">Valor da propriedade estática das palavras-chave (opcional)</span><span class="sxs-lookup"><span data-stu-id="cd8e7-205">Keywords static property value (optional)</span></span>

<span data-ttu-id="cd8e7-206">A chave **Palavras-chave** é enumerada, mas é possível usar um nome de propriedade estático na consulta da tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-206">The **Keywords** key is enumerated, but you can use a static property name in the hash table query.</span></span>
<span data-ttu-id="cd8e7-207">Em vez de usar a cadeia de caracteres retornada, o nome da propriedade deve ser convertido em um valor com a propriedade **Value__** .</span><span class="sxs-lookup"><span data-stu-id="cd8e7-207">Rather than using the returned string, the property name must be converted to a value with the **Value__** property.</span></span>

<span data-ttu-id="cd8e7-208">Por exemplo, o script a seguir usa a propriedade **Value__** .</span><span class="sxs-lookup"><span data-stu-id="cd8e7-208">For example, the following script uses the **Value__** property.</span></span>

```powershell
$C = [System.Diagnostics.Eventing.Reader.StandardEventKeywords]::EventLogClassic
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=$C.Value__
}
```

## <a name="filtering-by-event-id"></a><span data-ttu-id="cd8e7-209">Filtragem por ID do evento</span><span class="sxs-lookup"><span data-stu-id="cd8e7-209">Filtering by Event Id</span></span>

<span data-ttu-id="cd8e7-210">Para obter dados mais específicos, os resultados da consulta são filtrados por **ID do evento**. O **ID do evento** é referenciado na tabela de hash como o **ID** chave e o valor é um **ID de evento** específico. O **Visualizador de Eventos do Windows** exibe o **ID do evento**. Este exemplo usa o **ID do evento 1023**.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-210">To get more specific data, the query's results are filtered by **Event Id**. The **Event Id** is referenced in the hash table as the key **ID** and the value is a specific **Event Id**. The **Windows Event Viewer** displays the **Event Id**. This example uses **Event Id 1023**.</span></span>

<span data-ttu-id="cd8e7-211">Atualize a tabela de hash e inclua o par **chave-valor** com a chave, **ID** e o valor **1023**.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-211">Update the hash table and include the **key-value** pair with the key, **ID** and the value, **1023**.</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=36028797018963968
   ID=1023
}
```

## <a name="filtering-by-level"></a><span data-ttu-id="cd8e7-212">Filtragem por nível</span><span class="sxs-lookup"><span data-stu-id="cd8e7-212">Filtering by Level</span></span>

<span data-ttu-id="cd8e7-213">Para refinar ainda mais os resultados e incluir apenas os eventos de erros, use a chave **Nível**.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-213">To further refine the results and include only events that are errors, use the **Level** key.</span></span>
<span data-ttu-id="cd8e7-214">Embora seja um valor enumerado, o **Visualizador de Eventos do Windows** exibe o **Nível** como valores de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-214">**Windows Event Viewer** displays the **Level** as string values, but they are enumerated values.</span></span> <span data-ttu-id="cd8e7-215">Na tabela de hash, se você usar a chave **Nível** com um valor de cadeia de caracteres, será exibida uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-215">In the hash table, if you use the **Level** key with a string value, an error message is displayed.</span></span>

<span data-ttu-id="cd8e7-216">O **Nível** tem valores como **Erro**, **Aviso** ou **Informativo**.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-216">**Level** has values such as **Error**, **Warning**, or **Informational**.</span></span> <span data-ttu-id="cd8e7-217">Use o seguinte comando para exibir os nomes das propriedades `StandardEventLevel`.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-217">Use the following command to display the `StandardEventLevel` property names.</span></span>

```powershell
[System.Diagnostics.Eventing.Reader.StandardEventLevel] | Get-Member -Static -MemberType Property
```

```Output
   TypeName: System.Diagnostics.Eventing.Reader.StandardEventLevel

Name          MemberType Definition
----          ---------- ----------
Critical      Property   static System.Diagnostics.Eventing.Reader.StandardEventLevel Critical {get;}
Error         Property   static System.Diagnostics.Eventing.Reader.StandardEventLevel Error {get;}
Informational Property   static System.Diagnostics.Eventing.Reader.StandardEventLevel Informational {get;}
LogAlways     Property   static System.Diagnostics.Eventing.Reader.StandardEventLevel LogAlways {get;}
Verbose       Property   static System.Diagnostics.Eventing.Reader.StandardEventLevel Verbose {get;}
Warning       Property   static System.Diagnostics.Eventing.Reader.StandardEventLevel Warning {get;}
```

<span data-ttu-id="cd8e7-218">Os valores enumerados estão documentados no **.NET Framework**.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-218">The enumerated values are documented in the **.NET Framework**.</span></span> <span data-ttu-id="cd8e7-219">Para obter mais informações, confira [Enumeração de StandardEventKeywords](/dotnet/api/system.diagnostics.eventing.reader.standardeventlevel?redirectedfrom=MSDN&view=netframework-4.7.2).</span><span class="sxs-lookup"><span data-stu-id="cd8e7-219">For more information, see [StandardEventLevel Enumeration](/dotnet/api/system.diagnostics.eventing.reader.standardeventlevel?redirectedfrom=MSDN&view=netframework-4.7.2).</span></span>

<span data-ttu-id="cd8e7-220">Os nomes e valores enumerados de **Nível** são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="cd8e7-220">The **Level** key's names and enumerated values are as follows:</span></span>

| <span data-ttu-id="cd8e7-221">Nome</span><span class="sxs-lookup"><span data-stu-id="cd8e7-221">Name</span></span>           | <span data-ttu-id="cd8e7-222">Valor</span><span class="sxs-lookup"><span data-stu-id="cd8e7-222">Value</span></span> |
| -------------- | ----- |
| <span data-ttu-id="cd8e7-223">Verbose</span><span class="sxs-lookup"><span data-stu-id="cd8e7-223">Verbose</span></span>        |   <span data-ttu-id="cd8e7-224">5</span><span class="sxs-lookup"><span data-stu-id="cd8e7-224">5</span></span>   |
| <span data-ttu-id="cd8e7-225">Informativo</span><span class="sxs-lookup"><span data-stu-id="cd8e7-225">Informational</span></span>  |   <span data-ttu-id="cd8e7-226">4</span><span class="sxs-lookup"><span data-stu-id="cd8e7-226">4</span></span>   |
| <span data-ttu-id="cd8e7-227">Aviso</span><span class="sxs-lookup"><span data-stu-id="cd8e7-227">Warning</span></span>        |   <span data-ttu-id="cd8e7-228">3</span><span class="sxs-lookup"><span data-stu-id="cd8e7-228">3</span></span>   |
| <span data-ttu-id="cd8e7-229">Erro do</span><span class="sxs-lookup"><span data-stu-id="cd8e7-229">Error</span></span>          |   <span data-ttu-id="cd8e7-230">2</span><span class="sxs-lookup"><span data-stu-id="cd8e7-230">2</span></span>   |
| <span data-ttu-id="cd8e7-231">Crítico</span><span class="sxs-lookup"><span data-stu-id="cd8e7-231">Critical</span></span>       |   <span data-ttu-id="cd8e7-232">1</span><span class="sxs-lookup"><span data-stu-id="cd8e7-232">1</span></span>   |
| <span data-ttu-id="cd8e7-233">LogAlways</span><span class="sxs-lookup"><span data-stu-id="cd8e7-233">LogAlways</span></span>      |   <span data-ttu-id="cd8e7-234">0</span><span class="sxs-lookup"><span data-stu-id="cd8e7-234">0</span></span>   |

<span data-ttu-id="cd8e7-235">A tabela de hash para a consulta completa inclui a chave do **Nível** e o valor **2**.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-235">The hash table for the completed query includes the key, **Level**, and the value, **2**.</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=36028797018963968
   ID=1023
   Level=2
}
```

### <a name="level-static-property-in-enumeration-optional"></a><span data-ttu-id="cd8e7-236">Propriedade estática de nível na enumeração (opcional)</span><span class="sxs-lookup"><span data-stu-id="cd8e7-236">Level static property in enumeration (optional)</span></span>

<span data-ttu-id="cd8e7-237">A chave do **Nível** é enumerada, mas você pode usar um nome de propriedade estático na consulta da tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="cd8e7-237">The **Level** key is enumerated, but you can use a static property name in the hash table query.</span></span>
<span data-ttu-id="cd8e7-238">Em vez de usar a cadeia de caracteres retornada, o nome da propriedade deve ser convertido em um valor com a propriedade **Value__** .</span><span class="sxs-lookup"><span data-stu-id="cd8e7-238">Rather than using the returned string, the property name must be converted to a value with the **Value__** property.</span></span>

<span data-ttu-id="cd8e7-239">Por exemplo, o script a seguir usa a propriedade **Value__** .</span><span class="sxs-lookup"><span data-stu-id="cd8e7-239">For example, the following script uses the **Value__** property.</span></span>

```powershell
$C = [System.Diagnostics.Eventing.Reader.StandardEventLevel]::Informational
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=36028797018963968
   ID=1023
   Level=$C.Value__
}
```