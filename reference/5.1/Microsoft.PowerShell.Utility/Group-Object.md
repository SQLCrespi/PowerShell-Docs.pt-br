---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/group-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Group-Object
ms.openlocfilehash: df06d5cd83472c80a395e3dcf63c4d331c5da6bb
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "93195156"
---
# <span data-ttu-id="9fa99-103">Group-Object</span><span class="sxs-lookup"><span data-stu-id="9fa99-103">Group-Object</span></span>

## <span data-ttu-id="9fa99-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="9fa99-104">SYNOPSIS</span></span>
<span data-ttu-id="9fa99-105">Objetos de grupos que contêm o mesmo valor para as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="9fa99-105">Groups objects that contain the same value for specified properties.</span></span>

## <span data-ttu-id="9fa99-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9fa99-106">SYNTAX</span></span>

### <span data-ttu-id="9fa99-107">Tabela</span><span class="sxs-lookup"><span data-stu-id="9fa99-107">HashTable</span></span>

```
Group-Object [-NoElement] [-AsHashTable] [-AsString] [-InputObject <PSObject>]
 [[-Property] <Object[]>] [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## <span data-ttu-id="9fa99-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9fa99-108">DESCRIPTION</span></span>

<span data-ttu-id="9fa99-109">O `Group-Object` cmdlet exibe objetos em grupos com base no valor de uma propriedade especificada.</span><span class="sxs-lookup"><span data-stu-id="9fa99-109">The `Group-Object` cmdlet displays objects in groups based on the value of a specified property.</span></span>
<span data-ttu-id="9fa99-110">`Group-Object` Retorna uma tabela com uma linha para cada valor de propriedade e uma coluna que exibe o número de itens com esse valor.</span><span class="sxs-lookup"><span data-stu-id="9fa99-110">`Group-Object` returns a table with one row for each property value and a column that displays the number of items with that value.</span></span>

<span data-ttu-id="9fa99-111">Se você especificar mais de uma propriedade, `Group-Object` primeiro as agrupará pelos valores da primeira propriedade e, em seguida, dentro de cada grupo de propriedades, ela agrupará pelo valor da próxima propriedade.</span><span class="sxs-lookup"><span data-stu-id="9fa99-111">If you specify more than one property, `Group-Object` first groups them by the values of the first property, and then, within each property group, it groups by the value of the next property.</span></span>

## <span data-ttu-id="9fa99-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="9fa99-112">EXAMPLES</span></span>

### <span data-ttu-id="9fa99-113">Exemplo 1: agrupar arquivos por extensão</span><span class="sxs-lookup"><span data-stu-id="9fa99-113">Example 1: Group files by extension</span></span>

<span data-ttu-id="9fa99-114">Este exemplo obtém recursivamente os arquivos em `$PSHOME` e os agrupa por extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="9fa99-114">This example recursively gets the files under `$PSHOME` and groups them by file name extension.</span></span> <span data-ttu-id="9fa99-115">A saída é enviada para o `Sort-Object` cmdlet, que os classifica pela contagem de arquivos encontrados para a extensão fornecida.</span><span class="sxs-lookup"><span data-stu-id="9fa99-115">The output is sent to the `Sort-Object` cmdlet, which sorts them by the count files found for the given extension.</span></span> <span data-ttu-id="9fa99-116">O **nome** vazio representa diretórios.</span><span class="sxs-lookup"><span data-stu-id="9fa99-116">The empty **Name** represents directories.</span></span>

<span data-ttu-id="9fa99-117">Este exemplo usa o parâmetro **NoElement** para omitir os membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="9fa99-117">This example uses the **NoElement** parameter to omit the members of the group.</span></span>

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

### <span data-ttu-id="9fa99-118">Exemplo 2: agrupar inteiros por chances e até mesmo</span><span class="sxs-lookup"><span data-stu-id="9fa99-118">Example 2: Group integers by odds and evens</span></span>

<span data-ttu-id="9fa99-119">Este exemplo mostra como usar blocos de script como o valor do parâmetro **Property** .</span><span class="sxs-lookup"><span data-stu-id="9fa99-119">This example shows how to use script blocks as the value of the **Property** parameter.</span></span> <span data-ttu-id="9fa99-120">Esse comando exibe os inteiros de 1 a 20, agrupados por chances e até mesmo.</span><span class="sxs-lookup"><span data-stu-id="9fa99-120">This command displays the integers from 1 to 20, grouped by odds and even.</span></span>

```powershell
1..20 | Group-Object -Property {$_ % 2}
```

```Output
Count Name                      Group
----- ----                      -----
   10 0                         {2, 4, 6, 8...}
   10 1                         {1, 3, 5, 7...}
```

### <span data-ttu-id="9fa99-121">Exemplo 3: agrupar eventos de log de eventos por EntryType</span><span class="sxs-lookup"><span data-stu-id="9fa99-121">Example 3: Group event log events by EntryType</span></span>

<span data-ttu-id="9fa99-122">Este exemplo exibe as 1.000 entradas mais recentes no log de eventos do sistema, agrupadas por **EntryType** .</span><span class="sxs-lookup"><span data-stu-id="9fa99-122">This example displays the 1,000 most recent entries in the System event log, grouped by **EntryType** .</span></span>

<span data-ttu-id="9fa99-123">Na saída, a coluna **Count** representa o número de entradas em cada grupo.</span><span class="sxs-lookup"><span data-stu-id="9fa99-123">In the output, the **Count** column represents the number of entries in each group.</span></span> <span data-ttu-id="9fa99-124">A coluna **nome** representa os valores **EventType** que definem um grupo.</span><span class="sxs-lookup"><span data-stu-id="9fa99-124">The **Name** column represents the **EventType** values that define a group.</span></span> <span data-ttu-id="9fa99-125">A coluna **grupo** representa os objetos em cada grupo.</span><span class="sxs-lookup"><span data-stu-id="9fa99-125">The **Group** column represents the objects in each group.</span></span>

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

### <span data-ttu-id="9fa99-126">Exemplo 4: agrupar processos por classe de prioridade</span><span class="sxs-lookup"><span data-stu-id="9fa99-126">Example 4: Group processes by priority class</span></span>

<span data-ttu-id="9fa99-127">Este exemplo demonstra o efeito do parâmetro **NoElement** .</span><span class="sxs-lookup"><span data-stu-id="9fa99-127">This example demonstrates the effect of the **NoElement** parameter.</span></span> <span data-ttu-id="9fa99-128">Esses comandos agrupam os processos no computador por classe de prioridade.</span><span class="sxs-lookup"><span data-stu-id="9fa99-128">These commands group the processes on the computer by priority class.</span></span>

<span data-ttu-id="9fa99-129">O primeiro comando usa o `Get-Process` cmdlet para obter os processos no computador e envia os objetos por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="9fa99-129">The first command uses the `Get-Process` cmdlet to get the processes on the computer and sends the objects down the pipeline.</span></span> <span data-ttu-id="9fa99-130">`Group-Object`agrupa os objetos pelo valor da propriedade **PriorityClass** do processo.</span><span class="sxs-lookup"><span data-stu-id="9fa99-130">`Group-Object`groups the objects by the value of the **PriorityClass** property of the process.</span></span>

<span data-ttu-id="9fa99-131">O segundo exemplo usa o parâmetro **NoElement** para eliminar os membros do grupo da saída.</span><span class="sxs-lookup"><span data-stu-id="9fa99-131">The second example uses the **NoElement** parameter to eliminate the members of the group from the output.</span></span> <span data-ttu-id="9fa99-132">O resultado é uma tabela com apenas o valor da propriedade **Count** e **Name** .</span><span class="sxs-lookup"><span data-stu-id="9fa99-132">The result is a table with only the **Count** and **Name** property value.</span></span>

<span data-ttu-id="9fa99-133">Os resultados são mostrados na seguinte saída de exemplo.</span><span class="sxs-lookup"><span data-stu-id="9fa99-133">The results are shown in the following sample output.</span></span>

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

### <span data-ttu-id="9fa99-134">Exemplo 5: agrupar processos por nome</span><span class="sxs-lookup"><span data-stu-id="9fa99-134">Example 5: Group processes by name</span></span>

<span data-ttu-id="9fa99-135">O exemplo a seguir usa `Group-Object` para agrupar várias instâncias de processos em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="9fa99-135">The following example uses `Group-Object` to group multiple instances of processes running on the local computer.</span></span> <span data-ttu-id="9fa99-136">`Where-Object` exibe os processos com mais de uma instância.</span><span class="sxs-lookup"><span data-stu-id="9fa99-136">`Where-Object` displays processes with more than one instance.</span></span>

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

### <span data-ttu-id="9fa99-137">Exemplo 6: agrupar objetos em uma tabela de hash</span><span class="sxs-lookup"><span data-stu-id="9fa99-137">Example 6: Group objects in a hash table</span></span>

<span data-ttu-id="9fa99-138">Este exemplo usa os parâmetros **AsHashTable** e **AsString** para retornar os grupos em uma tabela de hash, como uma coleção de pares chave-valor.</span><span class="sxs-lookup"><span data-stu-id="9fa99-138">This example uses the **AsHashTable** and **AsString** parameters to return the groups in a hash table, as a collection of key-value pairs.</span></span>

<span data-ttu-id="9fa99-139">Na tabela de hash resultante, cada valor de propriedade é uma chave e os elementos de grupo são os valores.</span><span class="sxs-lookup"><span data-stu-id="9fa99-139">In the resulting hash table, each property value is a key, and the group elements are the values.</span></span>
<span data-ttu-id="9fa99-140">Como cada chave é uma propriedade do objeto de tabela de hash, você pode usar a notação de ponto para exibir os valores.</span><span class="sxs-lookup"><span data-stu-id="9fa99-140">Because each key is a property of the hash table object, you can use dot notation to display the values.</span></span>

<span data-ttu-id="9fa99-141">O primeiro comando obtém os `Get` `Set` cmdlets e na sessão, agrupa-os por verbo, retorna os grupos como uma tabela de hash e salva a tabela de hash na `$A` variável.</span><span class="sxs-lookup"><span data-stu-id="9fa99-141">The first command gets the `Get` and `Set` cmdlets in the session, groups them by verb, returns the groups as a hash table, and saves the hash table in the `$A` variable.</span></span>

<span data-ttu-id="9fa99-142">O segundo comando exibe a tabela de hash no `$A` .</span><span class="sxs-lookup"><span data-stu-id="9fa99-142">The second command displays the hash table in `$A`.</span></span> <span data-ttu-id="9fa99-143">Há dois pares chave-valor, um para os `Get` cmdlets e um para os `Set` cmdlets.</span><span class="sxs-lookup"><span data-stu-id="9fa99-143">There are two key-value pairs, one for the `Get` cmdlets and one for the `Set` cmdlets.</span></span>

<span data-ttu-id="9fa99-144">O terceiro comando usa a notação de ponto `$A.Get` para exibir os valores da chave **Get** em `$A` .</span><span class="sxs-lookup"><span data-stu-id="9fa99-144">The third command uses dot notation, `$A.Get` to display the values of the **Get** key in `$A`.</span></span> <span data-ttu-id="9fa99-145">Os valores são objeto **CmdletInfo** .</span><span class="sxs-lookup"><span data-stu-id="9fa99-145">The values are **CmdletInfo** object.</span></span> <span data-ttu-id="9fa99-146">O parâmetro **AsString** não converte os objetos nos grupos para cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9fa99-146">The **AsString** parameter doesn't convert the objects in the groups to strings.</span></span>

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
CommandType     Name                               Version    Source
-----------     ----                               -------    ------
Cmdlet          Get-Acl                            3.0.0.0    Microsoft.PowerShell.Security
Cmdlet          Get-Alias                          3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-AppLockerFileInformation       2.0.0.0    AppLocker
Cmdlet          Get-AppLockerPolicy                2.0.0.0    AppLocker
...
```

## <span data-ttu-id="9fa99-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9fa99-147">PARAMETERS</span></span>

### <span data-ttu-id="9fa99-148">-AsHashTable</span><span class="sxs-lookup"><span data-stu-id="9fa99-148">-AsHashTable</span></span>

<span data-ttu-id="9fa99-149">Indica que esse cmdlet retorna o grupo como uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="9fa99-149">Indicates that this cmdlet returns the group as a hash table.</span></span> <span data-ttu-id="9fa99-150">As chaves da tabela de hash são os valores de propriedade pelos quais os objetos são agrupados.</span><span class="sxs-lookup"><span data-stu-id="9fa99-150">The keys of the hash table are the property values by which the objects are grouped.</span></span> <span data-ttu-id="9fa99-151">Os valores da tabela de hash são os objetos que têm o valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="9fa99-151">The values of the hash table are the objects that have that property value.</span></span>

<span data-ttu-id="9fa99-152">Por si só, o parâmetro **AsHashTable** retorna cada tabela de hash na qual cada chave é uma instância do objeto agrupado.</span><span class="sxs-lookup"><span data-stu-id="9fa99-152">By itself, the **AsHashTable** parameter returns each hash table in which each key is an instance of the grouped object.</span></span> <span data-ttu-id="9fa99-153">Quando usado com o parâmetro **AsString** , as chaves na tabela de hash são cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9fa99-153">When used with the **AsString** parameter, the keys in the hash table are strings.</span></span>

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

### <span data-ttu-id="9fa99-154">-AsString</span><span class="sxs-lookup"><span data-stu-id="9fa99-154">-AsString</span></span>

<span data-ttu-id="9fa99-155">Indica que esse cmdlet converte as chaves da tabela de hash em cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9fa99-155">Indicates that this cmdlet converts the hash table keys to strings.</span></span> <span data-ttu-id="9fa99-156">Por padrão, as chaves de tabela de hash são instâncias de objeto agrupado.</span><span class="sxs-lookup"><span data-stu-id="9fa99-156">By default, the hash table keys are instances of the grouped object.</span></span> <span data-ttu-id="9fa99-157">Esse parâmetro é válido somente quando usado com o parâmetro **AsHashTable** .</span><span class="sxs-lookup"><span data-stu-id="9fa99-157">This parameter is valid only when used with the **AsHashTable** parameter.</span></span>

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

### <span data-ttu-id="9fa99-158">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="9fa99-158">-CaseSensitive</span></span>

<span data-ttu-id="9fa99-159">Indica que esse cmdlet torna o agrupamento diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="9fa99-159">Indicates that this cmdlet makes the grouping case-sensitive.</span></span> <span data-ttu-id="9fa99-160">Sem esse parâmetro, os valores de propriedade dos objetos em um grupo podem ter diferentes casos.</span><span class="sxs-lookup"><span data-stu-id="9fa99-160">Without this parameter, the property values of objects in a group might have different cases.</span></span>

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

### <span data-ttu-id="9fa99-161">-Culture</span><span class="sxs-lookup"><span data-stu-id="9fa99-161">-Culture</span></span>

<span data-ttu-id="9fa99-162">Especifica a cultura a ser usada ao comparar cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9fa99-162">Specifies the culture to use when comparing strings.</span></span>

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

### <span data-ttu-id="9fa99-163">-InputObject</span><span class="sxs-lookup"><span data-stu-id="9fa99-163">-InputObject</span></span>

<span data-ttu-id="9fa99-164">Especifica os objetos ao grupo.</span><span class="sxs-lookup"><span data-stu-id="9fa99-164">Specifies the objects to group.</span></span> <span data-ttu-id="9fa99-165">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="9fa99-165">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="9fa99-166">Quando você usa o parâmetro **InputObject** para enviar uma coleção de objetos ao `Group-Object` , o `Group-Object` recebe um objeto que representa a coleção.</span><span class="sxs-lookup"><span data-stu-id="9fa99-166">When you use the **InputObject** parameter to submit a collection of objects to `Group-Object`, `Group-Object` receives one object that represents the collection.</span></span> <span data-ttu-id="9fa99-167">Como resultado, ele cria um único grupo com esse objeto como seu membro.</span><span class="sxs-lookup"><span data-stu-id="9fa99-167">As a result, it creates a single group with that object as its member.</span></span>

<span data-ttu-id="9fa99-168">Para agrupar os objetos em uma coleção, redirecione os objetos para `Group-Object` .</span><span class="sxs-lookup"><span data-stu-id="9fa99-168">To group the objects in a collection, pipe the objects to `Group-Object`.</span></span>

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

### <span data-ttu-id="9fa99-169">-NoElement</span><span class="sxs-lookup"><span data-stu-id="9fa99-169">-NoElement</span></span>

<span data-ttu-id="9fa99-170">Indica que esse cmdlet omite os membros de um grupo dos resultados.</span><span class="sxs-lookup"><span data-stu-id="9fa99-170">Indicates that this cmdlet omits the members of a group from the results.</span></span>

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

### <span data-ttu-id="9fa99-171">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="9fa99-171">-Property</span></span>

<span data-ttu-id="9fa99-172">Especifica as propriedades de agrupamento.</span><span class="sxs-lookup"><span data-stu-id="9fa99-172">Specifies the properties for grouping.</span></span> <span data-ttu-id="9fa99-173">Os objetos são organizados em grupos com base no valor da propriedade especificada.</span><span class="sxs-lookup"><span data-stu-id="9fa99-173">The objects are arranged into groups based on the value of the specified property.</span></span>

<span data-ttu-id="9fa99-174">O valor do parâmetro **Property** pode ser uma nova propriedade calculada.</span><span class="sxs-lookup"><span data-stu-id="9fa99-174">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="9fa99-175">A propriedade calculada pode ser um bloco de script ou uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="9fa99-175">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="9fa99-176">Os pares de chave-valor válidos são:</span><span class="sxs-lookup"><span data-stu-id="9fa99-176">Valid key-value pairs are:</span></span>

- <span data-ttu-id="9fa99-177">Expressão- `<string>` ou `<script block>`</span><span class="sxs-lookup"><span data-stu-id="9fa99-177">Expression - `<string>` or `<script block>`</span></span>

<span data-ttu-id="9fa99-178">Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="9fa99-178">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="9fa99-179">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9fa99-179">CommonParameters</span></span>

<span data-ttu-id="9fa99-180">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9fa99-180">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9fa99-181">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9fa99-181">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9fa99-182">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="9fa99-182">INPUTS</span></span>

### <span data-ttu-id="9fa99-183">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="9fa99-183">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="9fa99-184">Você pode canalizar qualquer objeto para `Group-Object` .</span><span class="sxs-lookup"><span data-stu-id="9fa99-184">You can pipe any object to `Group-Object`.</span></span>

## <span data-ttu-id="9fa99-185">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="9fa99-185">OUTPUTS</span></span>

### <span data-ttu-id="9fa99-186">Microsoft. PowerShell. Commands. GroupInfo ou System. Collections. Hashtable</span><span class="sxs-lookup"><span data-stu-id="9fa99-186">Microsoft.PowerShell.Commands.GroupInfo or System.Collections.Hashtable</span></span>

<span data-ttu-id="9fa99-187">Quando você usa o parâmetro **AsHashTable** , o `Group-Object` retorna um objeto **Hashtable** .</span><span class="sxs-lookup"><span data-stu-id="9fa99-187">When you use the **AsHashTable** parameter, `Group-Object` returns a **Hashtable** object.</span></span>
<span data-ttu-id="9fa99-188">Caso contrário, ele retorna um objeto **GroupInfo** .</span><span class="sxs-lookup"><span data-stu-id="9fa99-188">Otherwise, it returns a **GroupInfo** object.</span></span>

## <span data-ttu-id="9fa99-189">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="9fa99-189">NOTES</span></span>

<span data-ttu-id="9fa99-190">Você pode usar o parâmetro **GroupBy** dos cmdlets de formatação, como `Format-Table` e `Format-List` , para agrupar objetos.</span><span class="sxs-lookup"><span data-stu-id="9fa99-190">You can use the **GroupBy** parameter of the formatting cmdlets, such as `Format-Table` and `Format-List`, to group objects.</span></span> <span data-ttu-id="9fa99-191">Ao contrário de `Group-Object` , que cria uma única tabela com uma linha para cada valor de propriedade, os parâmetros **GroupBy** criam uma tabela para cada valor de propriedade com uma linha para cada item que tem o valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="9fa99-191">Unlike `Group-Object`, which creates a single table with a row for each property value, the **GroupBy** parameters create a table for each property value with a row for each item that has the property value.</span></span>

<span data-ttu-id="9fa99-192">`Group-Object` não exige que os objetos que estão sendo agrupados sejam do mesmo tipo de estrutura Microsoft .NET.</span><span class="sxs-lookup"><span data-stu-id="9fa99-192">`Group-Object` doesn't require that the objects being grouped are of the same Microsoft .NET Framework type.</span></span> <span data-ttu-id="9fa99-193">Ao agrupar objetos de diferentes tipos de .NET Framework, `Group-Object` o usa as seguintes regras:</span><span class="sxs-lookup"><span data-stu-id="9fa99-193">When grouping objects of different .NET Framework types, `Group-Object` uses the following rules:</span></span>

- <span data-ttu-id="9fa99-194">Mesmos nomes e tipos de propriedade.</span><span class="sxs-lookup"><span data-stu-id="9fa99-194">Same Property Names and Types.</span></span>

  <span data-ttu-id="9fa99-195">Se os objetos têm uma propriedade com o nome especificado e os valores de propriedade o mesmo tipo .NET Framework, os valores de propriedade são agrupados usando as mesmas regras que devem ser usadas para objetos do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="9fa99-195">If the objects have a property with the specified name, and the property values have the same .NET Framework type, the property values are grouped by using the same rules that would be used for objects of the same type.</span></span>

- <span data-ttu-id="9fa99-196">Mesmos nomes de propriedade, tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="9fa99-196">Same Property Names, Different Types.</span></span>

  <span data-ttu-id="9fa99-197">Se os objetos tiverem uma propriedade com o nome especificado, mas os valores de propriedade tiverem um tipo de .NET Framework diferente em objetos diferentes, o `Group-Object` usará o tipo de .NET Framework da primeira ocorrência da propriedade como o tipo de .NET Framework para esse grupo de propriedades.</span><span class="sxs-lookup"><span data-stu-id="9fa99-197">If the objects have a property with the specified name, but the property values have a different .NET Framework type in different objects, `Group-Object` uses the .NET Framework type of the first occurrence of the property as the .NET Framework type for that property group.</span></span> <span data-ttu-id="9fa99-198">Quando um objeto tem uma propriedade com um tipo diferente, o valor da propriedade é convertido no tipo daquele grupo.</span><span class="sxs-lookup"><span data-stu-id="9fa99-198">When an object has a property with a different type, the property value is converted to the type for that group.</span></span> <span data-ttu-id="9fa99-199">Se a conversão de tipo falhar, o objeto não está incluído no grupo.</span><span class="sxs-lookup"><span data-stu-id="9fa99-199">If the type conversion fails, the object is not included in the group.</span></span>

- <span data-ttu-id="9fa99-200">Propriedades ausentes.</span><span class="sxs-lookup"><span data-stu-id="9fa99-200">Missing Properties.</span></span>

  <span data-ttu-id="9fa99-201">Objetos que não têm uma propriedade especificada não podem ser agrupados.</span><span class="sxs-lookup"><span data-stu-id="9fa99-201">Objects that don't have a specified property can't be grouped.</span></span> <span data-ttu-id="9fa99-202">Os objetos que não são agrupados aparecem na saída final do objeto **GroupInfo** em um grupo chamado `AutomationNull.Value` .</span><span class="sxs-lookup"><span data-stu-id="9fa99-202">Objects that aren't grouped appear in the final **GroupInfo** object output in a group named `AutomationNull.Value`.</span></span>

## <span data-ttu-id="9fa99-203">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="9fa99-203">RELATED LINKS</span></span>

[<span data-ttu-id="9fa99-204">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="9fa99-204">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="9fa99-205">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="9fa99-205">about_Hash_Tables</span></span>](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[<span data-ttu-id="9fa99-206">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="9fa99-206">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="9fa99-207">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="9fa99-207">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="9fa99-208">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="9fa99-208">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="9fa99-209">New-Object</span><span class="sxs-lookup"><span data-stu-id="9fa99-209">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="9fa99-210">Select-Object</span><span class="sxs-lookup"><span data-stu-id="9fa99-210">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="9fa99-211">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="9fa99-211">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="9fa99-212">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="9fa99-212">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="9fa99-213">Where-Object</span><span class="sxs-lookup"><span data-stu-id="9fa99-213">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
