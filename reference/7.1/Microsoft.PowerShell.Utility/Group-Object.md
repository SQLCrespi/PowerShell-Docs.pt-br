---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/group-object?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Group-Object
ms.openlocfilehash: 962380192a188ec51ee3861c2623d3143a182ef3
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "93195167"
---
# <span data-ttu-id="20a9a-103">Group-Object</span><span class="sxs-lookup"><span data-stu-id="20a9a-103">Group-Object</span></span>

## <span data-ttu-id="20a9a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="20a9a-104">SYNOPSIS</span></span>
<span data-ttu-id="20a9a-105">Objetos de grupos que contêm o mesmo valor para as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="20a9a-105">Groups objects that contain the same value for specified properties.</span></span>

## <span data-ttu-id="20a9a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="20a9a-106">SYNTAX</span></span>

### <span data-ttu-id="20a9a-107">Tabela</span><span class="sxs-lookup"><span data-stu-id="20a9a-107">HashTable</span></span>

```
Group-Object [-NoElement] [-AsHashTable] [-AsString] [-InputObject <PSObject>]
 [[-Property] <Object[]>] [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## <span data-ttu-id="20a9a-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="20a9a-108">DESCRIPTION</span></span>

<span data-ttu-id="20a9a-109">O `Group-Object` cmdlet exibe objetos em grupos com base no valor de uma propriedade especificada.</span><span class="sxs-lookup"><span data-stu-id="20a9a-109">The `Group-Object` cmdlet displays objects in groups based on the value of a specified property.</span></span>
<span data-ttu-id="20a9a-110">`Group-Object` Retorna uma tabela com uma linha para cada valor de propriedade e uma coluna que exibe o número de itens com esse valor.</span><span class="sxs-lookup"><span data-stu-id="20a9a-110">`Group-Object` returns a table with one row for each property value and a column that displays the number of items with that value.</span></span>

<span data-ttu-id="20a9a-111">Se você especificar mais de uma propriedade, `Group-Object` primeiro as agrupará pelos valores da primeira propriedade e, em seguida, dentro de cada grupo de propriedades, ela agrupará pelo valor da próxima propriedade.</span><span class="sxs-lookup"><span data-stu-id="20a9a-111">If you specify more than one property, `Group-Object` first groups them by the values of the first property, and then, within each property group, it groups by the value of the next property.</span></span>

<span data-ttu-id="20a9a-112">A partir do PowerShell 7, `Group-Object` o pode combinar os parâmetros **CaseSensitive** e **AsHashTable** para criar uma tabela de hash que diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="20a9a-112">Beginning in PowerShell 7, `Group-Object` can combine the **CaseSensitive** and **AsHashtable** parameters to create a case-sensitive hash table.</span></span> <span data-ttu-id="20a9a-113">As chaves da tabela de hash usam comparações que diferenciam maiúsculas de minúsculas e geram um objeto **System. Collections. Hashtable** .</span><span class="sxs-lookup"><span data-stu-id="20a9a-113">The hash table keys use case-sensitive comparisons and output a **System.Collections.Hashtable** object.</span></span>

## <span data-ttu-id="20a9a-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="20a9a-114">EXAMPLES</span></span>

### <span data-ttu-id="20a9a-115">Exemplo 1: agrupar arquivos por extensão</span><span class="sxs-lookup"><span data-stu-id="20a9a-115">Example 1: Group files by extension</span></span>

<span data-ttu-id="20a9a-116">Este exemplo obtém recursivamente os arquivos em `$PSHOME` e os agrupa por extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="20a9a-116">This example recursively gets the files under `$PSHOME` and groups them by file name extension.</span></span> <span data-ttu-id="20a9a-117">A saída é enviada para o `Sort-Object` cmdlet, que os classifica pela contagem de arquivos encontrados para a extensão fornecida.</span><span class="sxs-lookup"><span data-stu-id="20a9a-117">The output is sent to the `Sort-Object` cmdlet, which sorts them by the count files found for the given extension.</span></span> <span data-ttu-id="20a9a-118">O **nome** vazio representa diretórios.</span><span class="sxs-lookup"><span data-stu-id="20a9a-118">The empty **Name** represents directories.</span></span>

<span data-ttu-id="20a9a-119">Este exemplo usa o parâmetro **NoElement** para omitir os membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="20a9a-119">This example uses the **NoElement** parameter to omit the members of the group.</span></span>

```powershell
$files = Get-ChildItem -Path $PSHOME -Recurse
$files | Group-Object -Property extension -NoElement | Sort-Object -Property Count -Descending
```

```Output
Count Name
----- ----
  365 .xml
  231 .cdxml
  197
  169 .ps1xml
  142 .txt
  114 .psd1
   63 .psm1
   49 .xsd
   36 .dll
   15 .mfl
   15 .mof
...
```

### <span data-ttu-id="20a9a-120">Exemplo 2: agrupar inteiros por chances e até mesmo</span><span class="sxs-lookup"><span data-stu-id="20a9a-120">Example 2: Group integers by odds and evens</span></span>

<span data-ttu-id="20a9a-121">Este exemplo mostra como usar blocos de script como o valor do parâmetro **Property** .</span><span class="sxs-lookup"><span data-stu-id="20a9a-121">This example shows how to use script blocks as the value of the **Property** parameter.</span></span> <span data-ttu-id="20a9a-122">Esse comando exibe os inteiros de 1 a 20, agrupados por chances e até mesmo.</span><span class="sxs-lookup"><span data-stu-id="20a9a-122">This command displays the integers from 1 to 20, grouped by odds and even.</span></span>

```powershell
1..20 | Group-Object -Property {$_ % 2}
```

```Output
Count Name                      Group
----- ----                      -----
   10 0                         {2, 4, 6, 8...}
   10 1                         {1, 3, 5, 7...}
```

### <span data-ttu-id="20a9a-123">Exemplo 3: agrupar eventos de log de eventos por EntryType</span><span class="sxs-lookup"><span data-stu-id="20a9a-123">Example 3: Group event log events by EntryType</span></span>

<span data-ttu-id="20a9a-124">Este exemplo exibe as 1.000 entradas mais recentes no log de eventos do sistema, agrupadas por **EntryType** .</span><span class="sxs-lookup"><span data-stu-id="20a9a-124">This example displays the 1,000 most recent entries in the System event log, grouped by **EntryType** .</span></span>

<span data-ttu-id="20a9a-125">Na saída, a coluna **Count** representa o número de entradas em cada grupo.</span><span class="sxs-lookup"><span data-stu-id="20a9a-125">In the output, the **Count** column represents the number of entries in each group.</span></span> <span data-ttu-id="20a9a-126">A coluna **nome** representa os valores **EventType** que definem um grupo.</span><span class="sxs-lookup"><span data-stu-id="20a9a-126">The **Name** column represents the **EventType** values that define a group.</span></span> <span data-ttu-id="20a9a-127">A coluna **grupo** representa os objetos em cada grupo.</span><span class="sxs-lookup"><span data-stu-id="20a9a-127">The **Group** column represents the objects in each group.</span></span>

```powershell
Get-WinEvent -LogName System -MaxEvents 1000 | Group-Object -Property LevelDisplayName
```

```Output
Count Name          Group
----- ----          -----
  153 Error         {System.Diagnostics.Eventing.Reader.EventLogRecord, System.Diagnostics...}
  722 Information   {System.Diagnostics.Eventing.Reader.EventLogRecord, System.Diagnostics...}
  125 Warning       {System.Diagnostics.Eventing.Reader.EventLogRecord, System.Diagnostics...}
```

### <span data-ttu-id="20a9a-128">Exemplo 4: agrupar processos por classe de prioridade</span><span class="sxs-lookup"><span data-stu-id="20a9a-128">Example 4: Group processes by priority class</span></span>

<span data-ttu-id="20a9a-129">Este exemplo demonstra o efeito do parâmetro **NoElement** .</span><span class="sxs-lookup"><span data-stu-id="20a9a-129">This example demonstrates the effect of the **NoElement** parameter.</span></span> <span data-ttu-id="20a9a-130">Esses comandos agrupam os processos no computador por classe de prioridade.</span><span class="sxs-lookup"><span data-stu-id="20a9a-130">These commands group the processes on the computer by priority class.</span></span>

<span data-ttu-id="20a9a-131">O primeiro comando usa o `Get-Process` cmdlet para obter os processos no computador e envia os objetos por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="20a9a-131">The first command uses the `Get-Process` cmdlet to get the processes on the computer and sends the objects down the pipeline.</span></span> <span data-ttu-id="20a9a-132">`Group-Object`agrupa os objetos pelo valor da propriedade **PriorityClass** do processo.</span><span class="sxs-lookup"><span data-stu-id="20a9a-132">`Group-Object`groups the objects by the value of the **PriorityClass** property of the process.</span></span>

<span data-ttu-id="20a9a-133">O segundo exemplo usa o parâmetro **NoElement** para eliminar os membros do grupo da saída.</span><span class="sxs-lookup"><span data-stu-id="20a9a-133">The second example uses the **NoElement** parameter to eliminate the members of the group from the output.</span></span> <span data-ttu-id="20a9a-134">O resultado é uma tabela com apenas o valor da propriedade **Count** e **Name** .</span><span class="sxs-lookup"><span data-stu-id="20a9a-134">The result is a table with only the **Count** and **Name** property value.</span></span>

<span data-ttu-id="20a9a-135">Os resultados são mostrados na seguinte saída de exemplo.</span><span class="sxs-lookup"><span data-stu-id="20a9a-135">The results are shown in the following sample output.</span></span>

```powershell
Get-Process | Group-Object -Property PriorityClass
```

```Output
Count Name         Group
----- ----         -----
   55 Normal       {System.Diagnostics.Process (AdtAgent), System.Diagnosti...
    1              {System.Diagnostics.Process (Idle)}
    3 High         {System.Diagnostics.Process (Newproc), System.Diagnostic...
    2 BelowNormal  {System.Diagnostics.Process (winperf),
```

```powershell
Get-Process | Group-Object -Property PriorityClass -NoElement
```

```Output
Count Name
----- ----
   55 Normal
    1
    3 High
    2 BelowNormal
```

### <span data-ttu-id="20a9a-136">Exemplo 5: agrupar processos por nome</span><span class="sxs-lookup"><span data-stu-id="20a9a-136">Example 5: Group processes by name</span></span>

<span data-ttu-id="20a9a-137">O exemplo a seguir usa `Group-Object` para agrupar várias instâncias de processos em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="20a9a-137">The following example uses `Group-Object` to group multiple instances of processes running on the local computer.</span></span> <span data-ttu-id="20a9a-138">`Where-Object` exibe os processos com mais de uma instância.</span><span class="sxs-lookup"><span data-stu-id="20a9a-138">`Where-Object` displays processes with more than one instance.</span></span>

```powershell
Get-Process | Group-Object -Property Name -NoElement | Where-Object {$_.Count -gt 1}
```

```Output
Count Name
----- ----
2     csrss
5     svchost
2     winlogon
2     wmiprvse
```

### <span data-ttu-id="20a9a-139">Exemplo 6: agrupar objetos em uma tabela de hash</span><span class="sxs-lookup"><span data-stu-id="20a9a-139">Example 6: Group objects in a hash table</span></span>

<span data-ttu-id="20a9a-140">Este exemplo usa os parâmetros **AsHashTable** e **AsString** para retornar os grupos em uma tabela de hash, como uma coleção de pares chave-valor.</span><span class="sxs-lookup"><span data-stu-id="20a9a-140">This example uses the **AsHashTable** and **AsString** parameters to return the groups in a hash table, as a collection of key-value pairs.</span></span>

<span data-ttu-id="20a9a-141">Na tabela de hash resultante, cada valor de propriedade é uma chave e os elementos de grupo são os valores.</span><span class="sxs-lookup"><span data-stu-id="20a9a-141">In the resulting hash table, each property value is a key, and the group elements are the values.</span></span>
<span data-ttu-id="20a9a-142">Como cada chave é uma propriedade do objeto de tabela de hash, você pode usar a notação de ponto para exibir os valores.</span><span class="sxs-lookup"><span data-stu-id="20a9a-142">Because each key is a property of the hash table object, you can use dot notation to display the values.</span></span>

<span data-ttu-id="20a9a-143">O primeiro comando obtém os `Get` `Set` cmdlets e na sessão, agrupa-os por verbo, retorna os grupos como uma tabela de hash e salva a tabela de hash na `$A` variável.</span><span class="sxs-lookup"><span data-stu-id="20a9a-143">The first command gets the `Get` and `Set` cmdlets in the session, groups them by verb, returns the groups as a hash table, and saves the hash table in the `$A` variable.</span></span>

<span data-ttu-id="20a9a-144">O segundo comando exibe a tabela de hash no `$A` .</span><span class="sxs-lookup"><span data-stu-id="20a9a-144">The second command displays the hash table in `$A`.</span></span> <span data-ttu-id="20a9a-145">Há dois pares chave-valor, um para os `Get` cmdlets e um para os `Set` cmdlets.</span><span class="sxs-lookup"><span data-stu-id="20a9a-145">There are two key-value pairs, one for the `Get` cmdlets and one for the `Set` cmdlets.</span></span>

<span data-ttu-id="20a9a-146">O terceiro comando usa a notação de ponto `$A.Get` para exibir os valores da chave **Get** em `$A` .</span><span class="sxs-lookup"><span data-stu-id="20a9a-146">The third command uses dot notation, `$A.Get` to display the values of the **Get** key in `$A`.</span></span> <span data-ttu-id="20a9a-147">Os valores são objeto **CmdletInfo** .</span><span class="sxs-lookup"><span data-stu-id="20a9a-147">The values are **CmdletInfo** object.</span></span> <span data-ttu-id="20a9a-148">O parâmetro **AsString** não converte os objetos nos grupos para cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="20a9a-148">The **AsString** parameter doesn't convert the objects in the groups to strings.</span></span>

```powershell
$A = Get-Command Get-*, Set-* -CommandType cmdlet | Group-Object -Property Verb -AsHashTable -AsString
$A
```

```Output
Name     Value
----     -----
Get      {Get-Acl, Get-Alias, Get-AppLockerFileInformation, Get-AppLockerPolicy...}
Set      {Set-Acl, Set-Alias, Set-AppBackgroundTaskResourcePolicy, Set-AppLockerPolicy...}
```

```powershell
$A.Get
```

```Output
CommandType     Name                                Version    Source
-----------     ----                                -------    ------
Cmdlet          Get-Acl                             7.0.0.0    Microsoft.PowerShell.Security
Cmdlet          Get-Alias                           7.0.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-AppLockerFileInformation        2.0.0.0    AppLocker
Cmdlet          Get-AppLockerPolicy                 2.0.0.0    AppLocker
...
```

### <span data-ttu-id="20a9a-149">Exemplo 7: criar uma tabela de hash que diferencia maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="20a9a-149">Example 7: Create a case-sensitive hash table</span></span>

<span data-ttu-id="20a9a-150">Este exemplo combina os parâmetros **CaseSensitive** e **AsHashTable** para criar uma tabela de hash que diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="20a9a-150">This example combines the **CaseSensitive** and **AsHashTable** parameters to create a case-sensitive hash table.</span></span> <span data-ttu-id="20a9a-151">Os arquivos no exemplo têm extensões do `.txt` e do `.TXT` .</span><span class="sxs-lookup"><span data-stu-id="20a9a-151">The files in the example have extensions of `.txt` and `.TXT`.</span></span>

```powershell
$hash = Get-ChildItem -Path C:\Files | Group-Object -Property Extension -CaseSensitive -AsHashTable
$hash
```

```Output
Name           Value
----           -----
.TXT           {C:\Files\File7.TXT, C:\Files\File8.TXT, C:\Files\File9.TXT}
.txt           {C:\Files\file1.txt, C:\Files\file2.txt, C:\Files\file3.txt}
```

<span data-ttu-id="20a9a-152">A `$hash` variável armazena o objeto **System. Collections. Hashtable** .</span><span class="sxs-lookup"><span data-stu-id="20a9a-152">The `$hash` variable stores the **System.Collections.Hashtable** object.</span></span> <span data-ttu-id="20a9a-153">`Get-ChildItem` Obtém os nomes de arquivo do `C:\Files` diretório e envia os objetos **System. IO. FileInfo** para baixo do pipeline.</span><span class="sxs-lookup"><span data-stu-id="20a9a-153">`Get-ChildItem` gets the file names from the `C:\Files` directory and sends the **System.IO.FileInfo** objects down the pipeline.</span></span> <span data-ttu-id="20a9a-154">`Group-Object`agrupa os objetos usando a **extensão** de valor de **Propriedade** .</span><span class="sxs-lookup"><span data-stu-id="20a9a-154">`Group-Object` groups the objects using the **Property** value **Extension** .</span></span> <span data-ttu-id="20a9a-155">Os parâmetros **CaseSensitive** e **AsHashTable** criam a tabela de hash e as chaves são agrupadas usando as chaves que diferenciam maiúsculas de minúsculas `.txt` e `.TXT` .</span><span class="sxs-lookup"><span data-stu-id="20a9a-155">The **CaseSensitive** and **AsHashTable** parameters create the hash table and the keys are grouped using the case-sensitive keys `.txt` and `.TXT`.</span></span>

## <span data-ttu-id="20a9a-156">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="20a9a-156">PARAMETERS</span></span>

### <span data-ttu-id="20a9a-157">-AsHashTable</span><span class="sxs-lookup"><span data-stu-id="20a9a-157">-AsHashTable</span></span>

<span data-ttu-id="20a9a-158">Indica que esse cmdlet retorna o grupo como uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="20a9a-158">Indicates that this cmdlet returns the group as a hash table.</span></span> <span data-ttu-id="20a9a-159">As chaves da tabela de hash são os valores de propriedade pelos quais os objetos são agrupados.</span><span class="sxs-lookup"><span data-stu-id="20a9a-159">The keys of the hash table are the property values by which the objects are grouped.</span></span> <span data-ttu-id="20a9a-160">Os valores da tabela de hash são os objetos que têm o valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="20a9a-160">The values of the hash table are the objects that have that property value.</span></span>

<span data-ttu-id="20a9a-161">Por si só, o parâmetro **AsHashTable** retorna cada tabela de hash na qual cada chave é uma instância do objeto agrupado.</span><span class="sxs-lookup"><span data-stu-id="20a9a-161">By itself, the **AsHashTable** parameter returns each hash table in which each key is an instance of the grouped object.</span></span> <span data-ttu-id="20a9a-162">Quando usado com o parâmetro **AsString** , as chaves na tabela de hash são cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="20a9a-162">When used with the **AsString** parameter, the keys in the hash table are strings.</span></span>

<span data-ttu-id="20a9a-163">A partir do PowerShell 7, para criar tabelas de hash que diferenciam maiúsculas de minúsculas, inclua **CaseSensitive** e **AsHashTable** em seu comando.</span><span class="sxs-lookup"><span data-stu-id="20a9a-163">Beginning in PowerShell 7, to create case-sensitive hash tables, include **CaseSensitive** and **AsHashtable** in your command.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: AHT

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="20a9a-164">-AsString</span><span class="sxs-lookup"><span data-stu-id="20a9a-164">-AsString</span></span>

<span data-ttu-id="20a9a-165">Indica que esse cmdlet converte as chaves da tabela de hash em cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="20a9a-165">Indicates that this cmdlet converts the hash table keys to strings.</span></span> <span data-ttu-id="20a9a-166">Por padrão, as chaves de tabela de hash são instâncias de objeto agrupado.</span><span class="sxs-lookup"><span data-stu-id="20a9a-166">By default, the hash table keys are instances of the grouped object.</span></span> <span data-ttu-id="20a9a-167">Esse parâmetro é válido somente quando usado com o parâmetro **AsHashTable** .</span><span class="sxs-lookup"><span data-stu-id="20a9a-167">This parameter is valid only when used with the **AsHashTable** parameter.</span></span>

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

### <span data-ttu-id="20a9a-168">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="20a9a-168">-CaseSensitive</span></span>

<span data-ttu-id="20a9a-169">Indica que esse cmdlet torna o agrupamento diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="20a9a-169">Indicates that this cmdlet makes the grouping case-sensitive.</span></span> <span data-ttu-id="20a9a-170">Sem esse parâmetro, os valores de propriedade dos objetos em um grupo podem ter diferentes casos.</span><span class="sxs-lookup"><span data-stu-id="20a9a-170">Without this parameter, the property values of objects in a group might have different cases.</span></span>

<span data-ttu-id="20a9a-171">A partir do PowerShell 7, para criar tabelas de hash que diferenciam maiúsculas de minúsculas, inclua **CaseSensitive** e **AsHashTable** em seu comando.</span><span class="sxs-lookup"><span data-stu-id="20a9a-171">Beginning in PowerShell 7, to create case-sensitive hash tables, include **CaseSensitive** and **AsHashtable** in your command.</span></span>

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

### <span data-ttu-id="20a9a-172">-Culture</span><span class="sxs-lookup"><span data-stu-id="20a9a-172">-Culture</span></span>

<span data-ttu-id="20a9a-173">Especifica a cultura a ser usada ao comparar cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="20a9a-173">Specifies the culture to use when comparing strings.</span></span>

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

### <span data-ttu-id="20a9a-174">-InputObject</span><span class="sxs-lookup"><span data-stu-id="20a9a-174">-InputObject</span></span>

<span data-ttu-id="20a9a-175">Especifica os objetos ao grupo.</span><span class="sxs-lookup"><span data-stu-id="20a9a-175">Specifies the objects to group.</span></span> <span data-ttu-id="20a9a-176">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="20a9a-176">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="20a9a-177">Quando você usa o parâmetro **InputObject** para enviar uma coleção de objetos ao `Group-Object` , o `Group-Object` recebe um objeto que representa a coleção.</span><span class="sxs-lookup"><span data-stu-id="20a9a-177">When you use the **InputObject** parameter to submit a collection of objects to `Group-Object`, `Group-Object` receives one object that represents the collection.</span></span> <span data-ttu-id="20a9a-178">Como resultado, ele cria um único grupo com esse objeto como seu membro.</span><span class="sxs-lookup"><span data-stu-id="20a9a-178">As a result, it creates a single group with that object as its member.</span></span>

<span data-ttu-id="20a9a-179">Para agrupar os objetos em uma coleção, redirecione os objetos para `Group-Object` .</span><span class="sxs-lookup"><span data-stu-id="20a9a-179">To group the objects in a collection, pipe the objects to `Group-Object`.</span></span>

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

### <span data-ttu-id="20a9a-180">-NoElement</span><span class="sxs-lookup"><span data-stu-id="20a9a-180">-NoElement</span></span>

<span data-ttu-id="20a9a-181">Indica que esse cmdlet omite os membros de um grupo dos resultados.</span><span class="sxs-lookup"><span data-stu-id="20a9a-181">Indicates that this cmdlet omits the members of a group from the results.</span></span>

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

### <span data-ttu-id="20a9a-182">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="20a9a-182">-Property</span></span>

<span data-ttu-id="20a9a-183">Especifica as propriedades de agrupamento.</span><span class="sxs-lookup"><span data-stu-id="20a9a-183">Specifies the properties for grouping.</span></span> <span data-ttu-id="20a9a-184">Os objetos são organizados em grupos com base no valor da propriedade especificada.</span><span class="sxs-lookup"><span data-stu-id="20a9a-184">The objects are arranged into groups based on the value of the specified property.</span></span>

<span data-ttu-id="20a9a-185">O valor do parâmetro **Property** pode ser uma nova propriedade calculada.</span><span class="sxs-lookup"><span data-stu-id="20a9a-185">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="20a9a-186">A propriedade calculada pode ser um bloco de script ou uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="20a9a-186">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="20a9a-187">Os pares de chave-valor válidos são:</span><span class="sxs-lookup"><span data-stu-id="20a9a-187">Valid key-value pairs are:</span></span>

- <span data-ttu-id="20a9a-188">Expressão- `<string>` ou `<script block>`</span><span class="sxs-lookup"><span data-stu-id="20a9a-188">Expression - `<string>` or `<script block>`</span></span>

<span data-ttu-id="20a9a-189">Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="20a9a-189">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="20a9a-190">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="20a9a-190">CommonParameters</span></span>

<span data-ttu-id="20a9a-191">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="20a9a-191">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="20a9a-192">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="20a9a-192">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="20a9a-193">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="20a9a-193">INPUTS</span></span>

### <span data-ttu-id="20a9a-194">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="20a9a-194">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="20a9a-195">Você pode canalizar qualquer objeto para `Group-Object` .</span><span class="sxs-lookup"><span data-stu-id="20a9a-195">You can pipe any object to `Group-Object`.</span></span>

## <span data-ttu-id="20a9a-196">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="20a9a-196">OUTPUTS</span></span>

### <span data-ttu-id="20a9a-197">Microsoft. PowerShell. Commands. GroupInfo ou System. Collections. Hashtable</span><span class="sxs-lookup"><span data-stu-id="20a9a-197">Microsoft.PowerShell.Commands.GroupInfo or System.Collections.Hashtable</span></span>

<span data-ttu-id="20a9a-198">Quando você usa o parâmetro **AsHashTable** , o `Group-Object` retorna um objeto **Hashtable** .</span><span class="sxs-lookup"><span data-stu-id="20a9a-198">When you use the **AsHashTable** parameter, `Group-Object` returns a **Hashtable** object.</span></span>
<span data-ttu-id="20a9a-199">Caso contrário, ele retorna um objeto **GroupInfo** .</span><span class="sxs-lookup"><span data-stu-id="20a9a-199">Otherwise, it returns a **GroupInfo** object.</span></span>

## <span data-ttu-id="20a9a-200">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="20a9a-200">NOTES</span></span>

<span data-ttu-id="20a9a-201">Você pode usar o parâmetro **GroupBy** dos cmdlets de formatação, como `Format-Table` e `Format-List` , para agrupar objetos.</span><span class="sxs-lookup"><span data-stu-id="20a9a-201">You can use the **GroupBy** parameter of the formatting cmdlets, such as `Format-Table` and `Format-List`, to group objects.</span></span> <span data-ttu-id="20a9a-202">Ao contrário de `Group-Object` , que cria uma única tabela com uma linha para cada valor de propriedade, os parâmetros **GroupBy** criam uma tabela para cada valor de propriedade com uma linha para cada item que tem o valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="20a9a-202">Unlike `Group-Object`, which creates a single table with a row for each property value, the **GroupBy** parameters create a table for each property value with a row for each item that has the property value.</span></span>

<span data-ttu-id="20a9a-203">`Group-Object` não exige que os objetos que estão sendo agrupados sejam do mesmo tipo de núcleo Microsoft .NET.</span><span class="sxs-lookup"><span data-stu-id="20a9a-203">`Group-Object` doesn't require that the objects being grouped are of the same Microsoft .NET Core type.</span></span> <span data-ttu-id="20a9a-204">Ao agrupar objetos de diferentes tipos do .NET Core, `Group-Object` o usa as seguintes regras:</span><span class="sxs-lookup"><span data-stu-id="20a9a-204">When grouping objects of different .NET Core types, `Group-Object` uses the following rules:</span></span>

- <span data-ttu-id="20a9a-205">Mesmos nomes e tipos de propriedade.</span><span class="sxs-lookup"><span data-stu-id="20a9a-205">Same Property Names and Types.</span></span>

  <span data-ttu-id="20a9a-206">Se os objetos tiverem uma propriedade com o nome especificado e os valores de propriedade tiverem o mesmo tipo de núcleo .NET, os valores de propriedade serão agrupados usando as mesmas regras que seriam usadas para objetos do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="20a9a-206">If the objects have a property with the specified name, and the property values have the same .NET Core type, the property values are grouped by using the same rules that would be used for objects of the same type.</span></span>

- <span data-ttu-id="20a9a-207">Mesmos nomes de propriedade, tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="20a9a-207">Same Property Names, Different Types.</span></span>

  <span data-ttu-id="20a9a-208">Se os objetos tiverem uma propriedade com o nome especificado, mas os valores de propriedade tiverem um tipo .NET Core diferente em objetos diferentes, o `Group-Object` usará o tipo .NET Core da primeira ocorrência da propriedade como o tipo de núcleo do .net para esse grupo de propriedades.</span><span class="sxs-lookup"><span data-stu-id="20a9a-208">If the objects have a property with the specified name, but the property values have a different .NET Core type in different objects, `Group-Object` uses the .NET Core type of the first occurrence of the property as the .NET Core type for that property group.</span></span> <span data-ttu-id="20a9a-209">Quando um objeto tem uma propriedade com um tipo diferente, o valor da propriedade é convertido no tipo daquele grupo.</span><span class="sxs-lookup"><span data-stu-id="20a9a-209">When an object has a property with a different type, the property value is converted to the type for that group.</span></span> <span data-ttu-id="20a9a-210">Se a conversão de tipo falhar, o objeto não será incluído no grupo.</span><span class="sxs-lookup"><span data-stu-id="20a9a-210">If the type conversion fails, the object isn't included in the group.</span></span>

- <span data-ttu-id="20a9a-211">Propriedades ausentes.</span><span class="sxs-lookup"><span data-stu-id="20a9a-211">Missing Properties.</span></span>

  <span data-ttu-id="20a9a-212">Objetos que não têm uma propriedade especificada não podem ser agrupados.</span><span class="sxs-lookup"><span data-stu-id="20a9a-212">Objects that don't have a specified property can't be grouped.</span></span> <span data-ttu-id="20a9a-213">Os objetos que não são agrupados aparecem na saída final do objeto **GroupInfo** em um grupo chamado `AutomationNull.Value` .</span><span class="sxs-lookup"><span data-stu-id="20a9a-213">Objects that aren't grouped appear in the final **GroupInfo** object output in a group named `AutomationNull.Value`.</span></span>

## <span data-ttu-id="20a9a-214">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="20a9a-214">RELATED LINKS</span></span>

[<span data-ttu-id="20a9a-215">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="20a9a-215">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="20a9a-216">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="20a9a-216">about_Hash_Tables</span></span>](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[<span data-ttu-id="20a9a-217">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="20a9a-217">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="20a9a-218">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="20a9a-218">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="20a9a-219">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="20a9a-219">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="20a9a-220">New-Object</span><span class="sxs-lookup"><span data-stu-id="20a9a-220">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="20a9a-221">Select-Object</span><span class="sxs-lookup"><span data-stu-id="20a9a-221">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="20a9a-222">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="20a9a-222">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="20a9a-223">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="20a9a-223">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="20a9a-224">Where-Object</span><span class="sxs-lookup"><span data-stu-id="20a9a-224">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
