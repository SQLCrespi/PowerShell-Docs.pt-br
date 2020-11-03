---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/select-object?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Select-Object
ms.openlocfilehash: 5c27421180131562c6a2a1fe24d1a8203f4a9828
ms.sourcegitcommit: f9ae48d026d65833b9c8ca881058dda0bbd067b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "93195357"
---
# <span data-ttu-id="93ecc-103">Select-Object</span><span class="sxs-lookup"><span data-stu-id="93ecc-103">Select-Object</span></span>

## <span data-ttu-id="93ecc-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="93ecc-104">SYNOPSIS</span></span>
<span data-ttu-id="93ecc-105">Seleciona objetos ou propriedades de objeto.</span><span class="sxs-lookup"><span data-stu-id="93ecc-105">Selects objects or object properties.</span></span>

## <span data-ttu-id="93ecc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="93ecc-106">SYNTAX</span></span>

### <span data-ttu-id="93ecc-107">Defaultparameter (padrão)</span><span class="sxs-lookup"><span data-stu-id="93ecc-107">DefaultParameter (Default)</span></span>

```
Select-Object [-InputObject <PSObject>] [[-Property] <Object[]>] [-ExcludeProperty <String[]>]
 [-ExpandProperty <String>] [-Unique] [-Last <Int32>] [-First <Int32>] [-Skip <Int32>] [-Wait]
 [<CommonParameters>]
```

### <span data-ttu-id="93ecc-108">SkipLastParameter</span><span class="sxs-lookup"><span data-stu-id="93ecc-108">SkipLastParameter</span></span>

```
Select-Object [-InputObject <PSObject>] [[-Property] <Object[]>] [-ExcludeProperty <String[]>]
 [-ExpandProperty <String>] [-Unique] [-SkipLast <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="93ecc-109">IndexParameter</span><span class="sxs-lookup"><span data-stu-id="93ecc-109">IndexParameter</span></span>

```
Select-Object [-InputObject <PSObject>] [-Unique] [-Wait] [-Index <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="93ecc-110">SkipIndexParameter</span><span class="sxs-lookup"><span data-stu-id="93ecc-110">SkipIndexParameter</span></span>

```
Select-Object [-InputObject <PSObject>] [-Unique] [-SkipIndex <Int32[]>] [<CommonParameters>]
```

## <span data-ttu-id="93ecc-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="93ecc-111">DESCRIPTION</span></span>

<span data-ttu-id="93ecc-112">O `Select-Object` cmdlet seleciona as propriedades especificadas de um objeto ou conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="93ecc-112">The `Select-Object` cmdlet selects specified properties of an object or set of objects.</span></span> <span data-ttu-id="93ecc-113">Ele também pode selecionar objetos únicos, um número especificado de objetos, ou então objetos em uma posição especificada em uma matriz.</span><span class="sxs-lookup"><span data-stu-id="93ecc-113">It can also select unique objects, a specified number of objects, or objects in a specified position in an array.</span></span>

<span data-ttu-id="93ecc-114">Para selecionar objetos de uma coleção, use os parâmetros **First** , **Last** , **Unique** , **Skip** e **Index** .</span><span class="sxs-lookup"><span data-stu-id="93ecc-114">To select objects from a collection, use the **First** , **Last** , **Unique** , **Skip** , and **Index** parameters.</span></span> <span data-ttu-id="93ecc-115">Para selecionar as propriedades do objeto, use o parâmetro **Property** .</span><span class="sxs-lookup"><span data-stu-id="93ecc-115">To select object properties, use the **Property** parameter.</span></span> <span data-ttu-id="93ecc-116">Quando você seleciona propriedades, o `Select-Object` retorna novos objetos que têm apenas as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="93ecc-116">When you select properties, `Select-Object` returns new objects that have only the specified properties.</span></span>

<span data-ttu-id="93ecc-117">A partir do Windows PowerShell 3,0, `Select-Object` o inclui um recurso de otimização que impede que os comandos criem e processem objetos que não são usados.</span><span class="sxs-lookup"><span data-stu-id="93ecc-117">Beginning in Windows PowerShell 3.0, `Select-Object` includes an optimization feature that prevents commands from creating and processing objects that are not used.</span></span>

<span data-ttu-id="93ecc-118">Quando você inclui um `Select-Object` comando com os parâmetros **First** ou **index** em um pipeline de comando, o PowerShell interrompe o comando que gera os objetos assim que o número selecionado de objetos é gerado, mesmo quando o comando que gera os objetos é exibido antes do `Select-Object` comando no pipeline.</span><span class="sxs-lookup"><span data-stu-id="93ecc-118">When you include a `Select-Object` command with the **First** or **Index** parameters in a command pipeline, PowerShell stops the command that generates the objects as soon as the selected number of objects is generated, even when the command that generates the objects appears before the `Select-Object` command in the pipeline.</span></span> <span data-ttu-id="93ecc-119">Para desativar esse comportamento de otimização, use o parâmetro **Wait** .</span><span class="sxs-lookup"><span data-stu-id="93ecc-119">To turn off this optimizing behavior, use the **Wait** parameter.</span></span>

## <span data-ttu-id="93ecc-120">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="93ecc-120">EXAMPLES</span></span>

### <span data-ttu-id="93ecc-121">Exemplo 1: selecionar objetos por Propriedade</span><span class="sxs-lookup"><span data-stu-id="93ecc-121">Example 1: Select objects by property</span></span>

<span data-ttu-id="93ecc-122">Este exemplo cria objetos que têm as propriedades de **nome** , **ID** e conjunto de trabalho ( **WS** ) de objetos de processo.</span><span class="sxs-lookup"><span data-stu-id="93ecc-122">This example creates objects that have the **Name** , **ID** , and working set ( **WS** ) properties of process objects.</span></span>

```powershell
Get-Process | Select-Object -Property ProcessName, Id, WS
```

### <span data-ttu-id="93ecc-123">Exemplo 2: selecionar objetos por propriedade e formatar os resultados</span><span class="sxs-lookup"><span data-stu-id="93ecc-123">Example 2: Select objects by property and format the results</span></span>

<span data-ttu-id="93ecc-124">Este exemplo obtém informações sobre os módulos usados pelos processos no computador.</span><span class="sxs-lookup"><span data-stu-id="93ecc-124">This example gets information about the modules used by the processes on the computer.</span></span> <span data-ttu-id="93ecc-125">Ele usa `Get-Process` o cmdlet para obter o processo no computador.</span><span class="sxs-lookup"><span data-stu-id="93ecc-125">It uses `Get-Process` cmdlet to get the process on the computer.</span></span>

<span data-ttu-id="93ecc-126">Ele usa o `Select-Object` cmdlet para gerar uma matriz de `[System.Diagnostics.ProcessModule]` instâncias, conforme contido na propriedade **modules** de cada `System.Diagnostics.Process` saída de instância por `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="93ecc-126">It uses the `Select-Object` cmdlet to output an array of `[System.Diagnostics.ProcessModule]` instances as contained in the **Modules** property of each `System.Diagnostics.Process` instance output by `Get-Process`.</span></span>

<span data-ttu-id="93ecc-127">O parâmetro **Property** do `Select-Object` cmdlet seleciona os nomes dos processos.</span><span class="sxs-lookup"><span data-stu-id="93ecc-127">The **Property** parameter of the `Select-Object` cmdlet selects the process names.</span></span> <span data-ttu-id="93ecc-128">Isso adiciona uma `ProcessName` **notaproperty** a cada `[System.Diagnostics.ProcessModule]` instância e a popula com o valor da propriedade **ProcessName** do processo atual.</span><span class="sxs-lookup"><span data-stu-id="93ecc-128">This adds a `ProcessName` **NoteProperty** to every `[System.Diagnostics.ProcessModule]` instance and populates it with the value of current process's **ProcessName** property.</span></span>

<span data-ttu-id="93ecc-129">Por fim, `Format-List` o cmdlet é usado para exibir o nome e os módulos de cada processo em uma lista.</span><span class="sxs-lookup"><span data-stu-id="93ecc-129">Finally, `Format-List` cmdlet is used to display the name and modules of each process in a list.</span></span>

```powershell
Get-Process Explorer | Select-Object -Property ProcessName -ExpandProperty Modules | Format-List
```

```Output
ProcessName       : explorer
ModuleName        : explorer.exe
FileName          : C:\WINDOWS\explorer.exe
BaseAddress       : 140697278152704
ModuleMemorySize  : 3919872
EntryPointAddress : 140697278841168
FileVersionInfo   : File:             C:\WINDOWS\explorer.exe
                    InternalName:     explorer
                    OriginalFilename: EXPLORER.EXE.MUI
                    FileVersion:      10.0.17134.1 (WinBuild.160101.0800)
                    FileDescription:  Windows Explorer
                    Product:          Microsoft Windows Operating System
                    ProductVersion:   10.0.17134.1
...
```

### <span data-ttu-id="93ecc-130">Exemplo 3: selecionar processos usando a maior parte da memória</span><span class="sxs-lookup"><span data-stu-id="93ecc-130">Example 3: Select processes using the most memory</span></span>

<span data-ttu-id="93ecc-131">Este exemplo obtém os cinco processos que estão usando a maior parte da memória.</span><span class="sxs-lookup"><span data-stu-id="93ecc-131">This example gets the five processes that are using the most memory.</span></span> <span data-ttu-id="93ecc-132">O `Get-Process` cmdlet obtém os processos no computador.</span><span class="sxs-lookup"><span data-stu-id="93ecc-132">The `Get-Process` cmdlet gets the processes on the computer.</span></span> <span data-ttu-id="93ecc-133">O `Sort-Object` cmdlet classifica os processos de acordo com o uso de memória (conjunto de trabalho) e o `Select-Object` cmdlet seleciona apenas os últimos cinco membros da matriz de objetos resultante.</span><span class="sxs-lookup"><span data-stu-id="93ecc-133">The `Sort-Object` cmdlet sorts the processes according to memory (working set) usage, and the `Select-Object` cmdlet selects only the last five members of the resulting array of objects.</span></span>

<span data-ttu-id="93ecc-134">O parâmetro **Wait** não é necessário em comandos que incluem o `Sort-Object` cmdlet porque o `Sort-Object` processa todos os objetos e, em seguida, retorna uma coleção.</span><span class="sxs-lookup"><span data-stu-id="93ecc-134">The **Wait** parameter is not required in commands that include the `Sort-Object` cmdlet because `Sort-Object` processes all objects and then returns a collection.</span></span> <span data-ttu-id="93ecc-135">A `Select-Object` otimização está disponível apenas para comandos que retornam objetos individualmente à medida que são processados.</span><span class="sxs-lookup"><span data-stu-id="93ecc-135">The `Select-Object` optimization is available only for commands that return objects individually as they are processed.</span></span>

```powershell
Get-Process | Sort-Object -Property WS | Select-Object -Last 5
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VS(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
2866     320       33432      45764   203   222.41   1292 svchost
577      17        23676      50516   265    50.58   4388 WINWORD
826      11        75448      76712   188    19.77   3780 Ps
1367     14        73152      88736   216    61.69    676 Ps
1612     44        66080      92780   380   900.59   6132 INFOPATH
```

### <span data-ttu-id="93ecc-136">Exemplo 4: selecionar caracteres exclusivos de uma matriz</span><span class="sxs-lookup"><span data-stu-id="93ecc-136">Example 4: Select unique characters from an array</span></span>

<span data-ttu-id="93ecc-137">Este exemplo usa o parâmetro **exclusivo** de `Select-Object` para obter caracteres exclusivos de uma matriz de caracteres.</span><span class="sxs-lookup"><span data-stu-id="93ecc-137">This example uses the **Unique** parameter of `Select-Object` to get unique characters from an array of characters.</span></span>

```powershell
"a","b","c","a","a","a" | Select-Object -Unique
```

```Output
a
b
c
```

### <span data-ttu-id="93ecc-138">Exemplo 5: selecionar eventos mais recentes e mais antigos no log de eventos</span><span class="sxs-lookup"><span data-stu-id="93ecc-138">Example 5: Select newest and oldest events in the event log</span></span>

<span data-ttu-id="93ecc-139">Este exemplo obtém os primeiros (mais recentes) e os últimos eventos (mais antigos) no log de eventos do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93ecc-139">This example gets the first (newest) and last (oldest) events in the Windows PowerShell event log.</span></span>

<span data-ttu-id="93ecc-140">`Get-EventLog` Obtém todos os eventos no log do Windows PowerShell e os salva na `$a` variável.</span><span class="sxs-lookup"><span data-stu-id="93ecc-140">`Get-EventLog` gets all events in the Windows PowerShell log and saves them in the `$a` variable.</span></span>
<span data-ttu-id="93ecc-141">Em seguida, `$a` é canalizado para o `Select-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="93ecc-141">Then, `$a` is piped to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="93ecc-142">O `Select-Object` comando usa o parâmetro **index** para selecionar eventos da matriz de eventos na `$a` variável.</span><span class="sxs-lookup"><span data-stu-id="93ecc-142">The `Select-Object` command uses the **Index** parameter to select events from the array of events in the `$a` variable.</span></span> <span data-ttu-id="93ecc-143">O índice do primeiro evento é 0.</span><span class="sxs-lookup"><span data-stu-id="93ecc-143">The index of the first event is 0.</span></span> <span data-ttu-id="93ecc-144">O índice do último evento é o número de itens em `$a` menos 1.</span><span class="sxs-lookup"><span data-stu-id="93ecc-144">The index of the last event is the number of items in `$a` minus 1.</span></span>

```powershell
$a = Get-EventLog -LogName "Windows PowerShell"
$a | Select-Object -Index 0, ($A.count - 1)
```

### <span data-ttu-id="93ecc-145">Exemplo 6: selecionar tudo, exceto o primeiro objeto</span><span class="sxs-lookup"><span data-stu-id="93ecc-145">Example 6: Select all but the first object</span></span>

<span data-ttu-id="93ecc-146">Este exemplo cria uma nova PSSession em cada um dos computadores listados na Servers.txt arquivos, exceto para o primeiro.</span><span class="sxs-lookup"><span data-stu-id="93ecc-146">This example creates a new PSSession on each of the computers listed in the Servers.txt files, except for the first one.</span></span>

<span data-ttu-id="93ecc-147">`Select-Object` seleciona tudo, exceto o primeiro computador em uma lista de nomes de computador.</span><span class="sxs-lookup"><span data-stu-id="93ecc-147">`Select-Object` selects all but the first computer in a list of computer names.</span></span> <span data-ttu-id="93ecc-148">A lista de computadores resultante é definida como o valor do parâmetro **ComputerName** do `New-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="93ecc-148">The resulting list of computers is set as the value of the **ComputerName** parameter of the `New-PSSession` cmdlet.</span></span>

```powershell
New-PSSession -ComputerName (Get-Content Servers.txt | Select-Object -Skip 1)
```

### <span data-ttu-id="93ecc-149">Exemplo 7: renomear arquivos e selecionar vários para revisão</span><span class="sxs-lookup"><span data-stu-id="93ecc-149">Example 7: Rename files and select several to review</span></span>

<span data-ttu-id="93ecc-150">Este exemplo adiciona um sufixo "-ro" aos nomes base dos arquivos de texto que têm o atributo somente leitura e, em seguida, exibe os cinco primeiros arquivos para que o usuário possa ver uma amostra do efeito.</span><span class="sxs-lookup"><span data-stu-id="93ecc-150">This example adds a "-ro" suffix to the base names of text files that have the read-only attribute and then displays the first five files so the user can see a sample of the effect.</span></span>

<span data-ttu-id="93ecc-151">`Get-ChildItem` usa o parâmetro dinâmico **ReadOnly** para obter arquivos somente leitura.</span><span class="sxs-lookup"><span data-stu-id="93ecc-151">`Get-ChildItem` uses the **ReadOnly** dynamic parameter to get read-only files.</span></span> <span data-ttu-id="93ecc-152">Os arquivos resultantes são canalizados para o `Rename-Item` cmdlet, que renomeia o arquivo.</span><span class="sxs-lookup"><span data-stu-id="93ecc-152">The resulting files are piped to the `Rename-Item` cmdlet, which renames the file.</span></span> <span data-ttu-id="93ecc-153">Ele usa o parâmetro **PassThru** do `Rename-Item` para enviar os arquivos renomeados para o `Select-Object` cmdlet, que seleciona os primeiros 5 para exibição.</span><span class="sxs-lookup"><span data-stu-id="93ecc-153">It uses the **Passthru** parameter of `Rename-Item` to send the renamed files to the `Select-Object` cmdlet, which selects the first 5 for display.</span></span>

<span data-ttu-id="93ecc-154">O parâmetro **Wait** de `Select-Object` impede que o PowerShell interrompa o `Get-ChildItem` cmdlet depois de obter os primeiros cinco arquivos de texto somente leitura.</span><span class="sxs-lookup"><span data-stu-id="93ecc-154">The **Wait** parameter of `Select-Object` prevents PowerShell from stopping the `Get-ChildItem` cmdlet after it gets the first five read-only text files.</span></span> <span data-ttu-id="93ecc-155">Sem este parâmetro, somente os primeiros cinco arquivos somente leitura devem ser renomeados.</span><span class="sxs-lookup"><span data-stu-id="93ecc-155">Without this parameter, only the first five read-only files would be renamed.</span></span>

```powershell
Get-ChildItem *.txt -ReadOnly |
    Rename-Item -NewName {$_.BaseName + "-ro.txt"} -PassThru |
    Select-Object -First 5 -Wait
```

### <span data-ttu-id="93ecc-156">Exemplo 8: demonstrar as complexidades do parâmetro-ExpandProperty</span><span class="sxs-lookup"><span data-stu-id="93ecc-156">Example 8: Demonstrate the intricacies of the -ExpandProperty parameter</span></span>

<span data-ttu-id="93ecc-157">Este exemplo demonstra as complexidades do parâmetro **ExpandProperty** .</span><span class="sxs-lookup"><span data-stu-id="93ecc-157">This example demonstrates the intricacies of the **ExpandProperty** parameter.</span></span>

<span data-ttu-id="93ecc-158">Observe que a saída gerada foi uma matriz de `[System.Int32]` instâncias.</span><span class="sxs-lookup"><span data-stu-id="93ecc-158">Note that the output generated was an array of `[System.Int32]` instances.</span></span> <span data-ttu-id="93ecc-159">As instâncias estão em conformidade com as regras de formatação padrão da **exibição de saída** .</span><span class="sxs-lookup"><span data-stu-id="93ecc-159">The instances conform to standard formatting rules of the **Output View** .</span></span> <span data-ttu-id="93ecc-160">Isso é verdadeiro para todas as propriedades *expandidas* .</span><span class="sxs-lookup"><span data-stu-id="93ecc-160">This is true for any *Expanded* properties.</span></span> <span data-ttu-id="93ecc-161">Se os objetos enviados tiverem um formato padrão específico, a propriedade expandida poderá não estar visível.</span><span class="sxs-lookup"><span data-stu-id="93ecc-161">If the outputted objects have a specific standard format, the expanded property might not be visible.</span></span>

```powershell
# Create a custom object to use for the Select-Object example.
$object = [pscustomobject]@{Name="CustomObject";Expand=@(1,2,3,4,5)}
# Use the ExpandProperty parameter to Expand the property.
$object | Select-Object -ExpandProperty Expand -Property Name
```

```Output
1
2
3
4
5
```

```powershell
# The output did not contain the Name property, but it was added successfully.
# Use Get-Member to confirm the Name property was added and populated.
$object | Select-Object -ExpandProperty Expand -Property Name | Get-Member
```

```Output
   TypeName: System.Int32

Name        MemberType   Definition
----        ----------   ----------
CompareTo   Method       int CompareTo(System.Object value), int CompareTo(int value), int IComparable.CompareTo(System.Object obj)...
Equals      Method       bool Equals(System.Object obj), bool Equals(int obj), bool IEquatable[int].Equals(int other)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
GetTypeCode Method       System.TypeCode GetTypeCode(), System.TypeCode IConvertible.GetTypeCode()
ToBoolean   Method       bool IConvertible.ToBoolean(System.IFormatProvider provider)
ToByte      Method       byte IConvertible.ToByte(System.IFormatProvider provider)
ToChar      Method       char IConvertible.ToChar(System.IFormatProvider provider)
ToDateTime  Method       datetime IConvertible.ToDateTime(System.IFormatProvider provider)
ToDecimal   Method       decimal IConvertible.ToDecimal(System.IFormatProvider provider)
ToDouble    Method       double IConvertible.ToDouble(System.IFormatProvider provider)
ToInt16     Method       int16 IConvertible.ToInt16(System.IFormatProvider provider)
ToInt32     Method       int IConvertible.ToInt32(System.IFormatProvider provider)
ToInt64     Method       long IConvertible.ToInt64(System.IFormatProvider provider)
ToSByte     Method       sbyte IConvertible.ToSByte(System.IFormatProvider provider)
ToSingle    Method       float IConvertible.ToSingle(System.IFormatProvider provider)
ToString    Method       string ToString(), string ToString(string format), string ToString(System.IFormatProvider provider)...
ToType      Method       System.Object IConvertible.ToType(type conversionType, System.IFormatProvider provider)
ToUInt16    Method       uint16 IConvertible.ToUInt16(System.IFormatProvider provider)
ToUInt32    Method       uint32 IConvertible.ToUInt32(System.IFormatProvider provider)
ToUInt64    Method       uint64 IConvertible.ToUInt64(System.IFormatProvider provider)
Name        NoteProperty string Name=CustomObject
```

### <span data-ttu-id="93ecc-162">Exemplo 9: criar propriedades personalizadas em objetos</span><span class="sxs-lookup"><span data-stu-id="93ecc-162">Example 9: Create custom properties on objects</span></span>

<span data-ttu-id="93ecc-163">O exemplo a seguir demonstra `Select-Object` como usar o para adicionar uma propriedade personalizada a qualquer objeto.</span><span class="sxs-lookup"><span data-stu-id="93ecc-163">The following example demonstrates using `Select-Object` to add a custom property to any object.</span></span>
<span data-ttu-id="93ecc-164">Quando você especifica um nome de propriedade que não existe, o `Select-Object` cria essa propriedade como uma **observaçãoproperty** em cada objeto passado.</span><span class="sxs-lookup"><span data-stu-id="93ecc-164">When you specify a property name that does not exist, `Select-Object` creates that property as a **NoteProperty** on each object passed.</span></span>

```powershell
$customObject = 1 | Select-Object -Property MyCustomProperty
$customObject.MyCustomProperty = "New Custom Property"
$customObject
```

```Output
MyCustomProperty
----------------
New Custom Property
```

### <span data-ttu-id="93ecc-165">Exemplo 10: criar propriedades calculadas para cada InputObject</span><span class="sxs-lookup"><span data-stu-id="93ecc-165">Example 10: Create calculated properties for each InputObject</span></span>

<span data-ttu-id="93ecc-166">Este exemplo demonstra `Select-Object` como usar o para adicionar propriedades calculadas à sua entrada.</span><span class="sxs-lookup"><span data-stu-id="93ecc-166">This example demonstrates using `Select-Object` to add calculated properties to your input.</span></span> <span data-ttu-id="93ecc-167">Passar um **scriptblock** para o parâmetro **Property** faz com que o `Select-Object` avalie a expressão em cada objeto passado e adicione os resultados à saída.</span><span class="sxs-lookup"><span data-stu-id="93ecc-167">Passing a **ScriptBlock** to the **Property** parameter causes `Select-Object` to evaluate the expression on each object passed and add the results to the output.</span></span> <span data-ttu-id="93ecc-168">Dentro do **scriptblock** , você pode usar a `$_` variável para fazer referência ao objeto atual no pipeline.</span><span class="sxs-lookup"><span data-stu-id="93ecc-168">Within the **ScriptBlock** , you can use the `$_` variable to reference the current object in the pipeline.</span></span>

<span data-ttu-id="93ecc-169">Por padrão, `Select-Object` o usará a cadeia de **scriptblock** como o nome da propriedade.</span><span class="sxs-lookup"><span data-stu-id="93ecc-169">By default, `Select-Object` will use the **ScriptBlock** string as the name of the property.</span></span> <span data-ttu-id="93ecc-170">Usando uma **tabela de hash** , você pode rotular a saída do **scriptblock** como uma propriedade personalizada adicionada a cada objeto.</span><span class="sxs-lookup"><span data-stu-id="93ecc-170">Using a **Hashtable** , you can label the output of your **ScriptBlock** as a custom property added to each object.</span></span> <span data-ttu-id="93ecc-171">Você pode adicionar várias propriedades calculadas a cada objeto passado para `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="93ecc-171">You can add multiple calculated properties to each object passed to `Select-Object`.</span></span>

```powershell
# Create a calculated property called $_.StartTime.DayOfWeek
Get-Process | Select-Object -Property ProcessName,{$_.StartTime.DayOfWeek}
```

```Output
ProcessName  $_.StartTime.DayOfWeek
----         ----------------------
alg                       Wednesday
ati2evxx                  Wednesday
ati2evxx                   Thursday
...
```

```powershell
# Add a custom property to calculate the size in KiloBytes of each FileInfo object you pass in.
# Use the pipeline variable to divide each file's length by 1 KiloBytes
$size = @{label="Size(KB)";expression={$_.length/1KB}}
# Create an additional calculated property with the number of Days since the file was last accessed.
# You can also shorten the key names to be 'l', and 'e', or use Name instead of Label.
$days = @{l="Days";e={((Get-Date) - $_.LastAccessTime).Days}}
# You can also shorten the name of your label key to 'l' and your expression key to 'e'.
Get-ChildItem $PSHOME -File | Select-Object Name, $size, $days
```

```Output
Name                        Size(KB)        Days
----                        --------        ----
Certificate.format.ps1xml   12.5244140625   223
Diagnostics.Format.ps1xml   4.955078125     223
DotNetTypes.format.ps1xml   134.9833984375  223
```

## <span data-ttu-id="93ecc-172">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="93ecc-172">PARAMETERS</span></span>

### <span data-ttu-id="93ecc-173">-ExcludeProperty</span><span class="sxs-lookup"><span data-stu-id="93ecc-173">-ExcludeProperty</span></span>

<span data-ttu-id="93ecc-174">Especifica as propriedades que esse cmdlet exclui da operação.</span><span class="sxs-lookup"><span data-stu-id="93ecc-174">Specifies the properties that this cmdlet excludes from the operation.</span></span> <span data-ttu-id="93ecc-175">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="93ecc-175">Wildcards are permitted.</span></span>

<span data-ttu-id="93ecc-176">A partir do PowerShell 6, não é mais necessário incluir o parâmetro **Property** para que o **ExcludeProperty** funcione.</span><span class="sxs-lookup"><span data-stu-id="93ecc-176">Beginning in PowerShell 6, it is no longer required to include the **Property** parameter for **ExcludeProperty** to work.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DefaultParameter, SkipLastParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="93ecc-177">-ExpandProperty</span><span class="sxs-lookup"><span data-stu-id="93ecc-177">-ExpandProperty</span></span>

<span data-ttu-id="93ecc-178">Especifica uma propriedade a selecionar e indica que deve-se tentar expandir essa propriedade.</span><span class="sxs-lookup"><span data-stu-id="93ecc-178">Specifies a property to select, and indicates that an attempt should be made to expand that property.</span></span>

- <span data-ttu-id="93ecc-179">Se a propriedade especificada for uma matriz, cada valor da matriz será incluído na saída.</span><span class="sxs-lookup"><span data-stu-id="93ecc-179">If the specified property is an array, each value of the array is included in the output.</span></span>
- <span data-ttu-id="93ecc-180">Se a propriedade especificada for um objeto, as propriedades de objetos serão expandidas para cada **InputObject**</span><span class="sxs-lookup"><span data-stu-id="93ecc-180">If the specified property is an object, the objects properties are expanded for every **InputObject**</span></span>

<span data-ttu-id="93ecc-181">Em ambos os casos, o **tipo** de saída de objetos corresponderá ao **tipo** da propriedade expandida.</span><span class="sxs-lookup"><span data-stu-id="93ecc-181">In either case, the **Type** of objects output will match the **Type** of the expanded property.</span></span>

<span data-ttu-id="93ecc-182">Se o parâmetro **Property** for especificado, o `Select-Object` tentará adicionar cada propriedade selecionada como uma **NoteProperty** a cada objeto de saída.</span><span class="sxs-lookup"><span data-stu-id="93ecc-182">If the **Property** parameter is specified, `Select-Object` will attempt to add each selected property as a **NoteProperty** to every outputted object.</span></span>

> [!WARNING]
> <span data-ttu-id="93ecc-183">Se você receber o erro: SELECT: a propriedade não pode ser processada porque `<PropertyName>` a propriedade já existe, considere o seguinte.</span><span class="sxs-lookup"><span data-stu-id="93ecc-183">If you receive the error: Select : Property cannot be processed because property `<PropertyName>` already exists, consider the following.</span></span>
> <span data-ttu-id="93ecc-184">Observe que, ao `-ExpandProperty` usar `Select-Object` o, não é possível substituir uma propriedade existente.</span><span class="sxs-lookup"><span data-stu-id="93ecc-184">Note that when using `-ExpandProperty`, `Select-Object` can not replace an existing property.</span></span>
> <span data-ttu-id="93ecc-185">Isso significa:</span><span class="sxs-lookup"><span data-stu-id="93ecc-185">This means:</span></span>
>
> - <span data-ttu-id="93ecc-186">Se o objeto expandido tiver uma propriedade de mesmo nome, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="93ecc-186">If the expanded object has a property of the same name, an error will occur.</span></span>
> - <span data-ttu-id="93ecc-187">Se o objeto *selecionado* tiver uma propriedade de mesmo nome que uma propriedade de objetos *expandida* , ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="93ecc-187">If the *Selected* object has a property of the same name as an *Expanded* objects property, an error will occur.</span></span>

```yaml
Type: System.String
Parameter Sets: DefaultParameter, SkipLastParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93ecc-188">-Primeiro</span><span class="sxs-lookup"><span data-stu-id="93ecc-188">-First</span></span>

<span data-ttu-id="93ecc-189">Especifica o número de objetos a selecionar desde o início de uma matriz de objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="93ecc-189">Specifies the number of objects to select from the beginning of an array of input objects.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93ecc-190">-Índice</span><span class="sxs-lookup"><span data-stu-id="93ecc-190">-Index</span></span>

<span data-ttu-id="93ecc-191">Seleciona objetos de uma matriz com base nos valores de índice desses objetos.</span><span class="sxs-lookup"><span data-stu-id="93ecc-191">Selects objects from an array based on their index values.</span></span> <span data-ttu-id="93ecc-192">Digite os índices separados por vírgulas em uma lista.</span><span class="sxs-lookup"><span data-stu-id="93ecc-192">Enter the indexes in a comma-separated list.</span></span> <span data-ttu-id="93ecc-193">Os índices em uma matriz começam com 0, onde 0 representa o primeiro valor e (n-1) representa o último valor.</span><span class="sxs-lookup"><span data-stu-id="93ecc-193">Indexes in an array begin with 0, where 0 represents the first value and (n-1) represents the last value.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: IndexParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93ecc-194">-InputObject</span><span class="sxs-lookup"><span data-stu-id="93ecc-194">-InputObject</span></span>

<span data-ttu-id="93ecc-195">Especifica os objetos a enviar ao cmdlet pelo pipeline.</span><span class="sxs-lookup"><span data-stu-id="93ecc-195">Specifies objects to send to the cmdlet through the pipeline.</span></span> <span data-ttu-id="93ecc-196">Esse parâmetro permite canalizar objetos para o `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="93ecc-196">This parameter enables you to pipe objects to `Select-Object`.</span></span>

<span data-ttu-id="93ecc-197">Quando você passa objetos para o parâmetro **InputObject** , em vez de usar o pipeline, `Select-Object` o trata o **InputObject** como um único objeto, mesmo que o valor seja uma coleção.</span><span class="sxs-lookup"><span data-stu-id="93ecc-197">When you pass objects to the **InputObject** parameter, instead of using the pipeline, `Select-Object` treats the **InputObject** as a single object, even if the value is a collection.</span></span> <span data-ttu-id="93ecc-198">É recomendável que você use o pipeline ao passar coleções para o `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="93ecc-198">It is recommended that you use the pipeline when passing collections to `Select-Object`.</span></span>

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

### <span data-ttu-id="93ecc-199">-Último</span><span class="sxs-lookup"><span data-stu-id="93ecc-199">-Last</span></span>

<span data-ttu-id="93ecc-200">Especifica o número de objetos a selecionar desde o final de uma matriz de objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="93ecc-200">Specifies the number of objects to select from the end of an array of input objects.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93ecc-201">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="93ecc-201">-Property</span></span>

<span data-ttu-id="93ecc-202">Especifica as propriedades a selecionar.</span><span class="sxs-lookup"><span data-stu-id="93ecc-202">Specifies the properties to select.</span></span> <span data-ttu-id="93ecc-203">Essas propriedades são adicionadas como membros da **observaçãoproperty** aos objetos de saída.</span><span class="sxs-lookup"><span data-stu-id="93ecc-203">These properties are added as **NoteProperty** members to the output objects.</span></span> <span data-ttu-id="93ecc-204">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="93ecc-204">Wildcards are permitted.</span></span>

<span data-ttu-id="93ecc-205">O valor do parâmetro **Property** pode ser uma nova propriedade calculada.</span><span class="sxs-lookup"><span data-stu-id="93ecc-205">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="93ecc-206">Para criar uma propriedade calculada, use uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="93ecc-206">To create a calculated, property, use a hash table.</span></span>

<span data-ttu-id="93ecc-207">As chaves válidas são:</span><span class="sxs-lookup"><span data-stu-id="93ecc-207">Valid keys are:</span></span>

- <span data-ttu-id="93ecc-208">Nome (ou rótulo)- `<string>`</span><span class="sxs-lookup"><span data-stu-id="93ecc-208">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="93ecc-209">Expressão- `<string>` ou `<script block>`</span><span class="sxs-lookup"><span data-stu-id="93ecc-209">Expression - `<string>` or `<script block>`</span></span>

<span data-ttu-id="93ecc-210">Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="93ecc-210">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: DefaultParameter, SkipLastParameter
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="93ecc-211">-Ignorar</span><span class="sxs-lookup"><span data-stu-id="93ecc-211">-Skip</span></span>

<span data-ttu-id="93ecc-212">Ignora (não seleciona) o número de itens especificado.</span><span class="sxs-lookup"><span data-stu-id="93ecc-212">Skips (does not select) the specified number of items.</span></span> <span data-ttu-id="93ecc-213">Por padrão, o parâmetro **Skip** conta a partir do início da matriz ou da lista de objetos, mas se o comando usar o **último** parâmetro, ele contará do final da lista ou da matriz.</span><span class="sxs-lookup"><span data-stu-id="93ecc-213">By default, the **Skip** parameter counts from the beginning of the array or list of objects, but if the command uses the **Last** parameter, it counts from the end of the list or array.</span></span>

<span data-ttu-id="93ecc-214">Ao contrário do parâmetro **Index** , que inicia a contagem em 0, o parâmetro **Skip** começa em 1.</span><span class="sxs-lookup"><span data-stu-id="93ecc-214">Unlike the **Index** parameter, which starts counting at 0, the **Skip** parameter begins at 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93ecc-215">-SkipLast</span><span class="sxs-lookup"><span data-stu-id="93ecc-215">-SkipLast</span></span>

<span data-ttu-id="93ecc-216">Ignora (não seleciona) o número especificado de itens do final da lista ou da matriz.</span><span class="sxs-lookup"><span data-stu-id="93ecc-216">Skips (does not select) the specified number of items from the end of the list or array.</span></span> <span data-ttu-id="93ecc-217">Funciona da mesma maneira que o uso de **Skip** junto com o **último** parâmetro.</span><span class="sxs-lookup"><span data-stu-id="93ecc-217">Works in the same way as using **Skip** together with **Last** parameter.</span></span>

<span data-ttu-id="93ecc-218">Ao contrário do parâmetro de **índice** , que inicia a contagem em 0, o parâmetro **SkipLast** começa em 1.</span><span class="sxs-lookup"><span data-stu-id="93ecc-218">Unlike the **Index** parameter, which starts counting at 0, the **SkipLast** parameter begins at 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: SkipLastParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93ecc-219">-Exclusivo</span><span class="sxs-lookup"><span data-stu-id="93ecc-219">-Unique</span></span>

<span data-ttu-id="93ecc-220">Especifica que, se um subconjunto dos objetos de entrada tem valores e propriedades idênticos, apenas um único membro do subconjunto será selecionado.</span><span class="sxs-lookup"><span data-stu-id="93ecc-220">Specifies that if a subset of the input objects has identical properties and values, only a single member of the subset will be selected.</span></span>

<span data-ttu-id="93ecc-221">Este parâmetro diferencia maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="93ecc-221">This parameter is case-sensitive.</span></span> <span data-ttu-id="93ecc-222">Como resultado, cadeias de caracteres que diferem apenas em maiúsculas e minúsculas são consideradas como sendo exclusivas.</span><span class="sxs-lookup"><span data-stu-id="93ecc-222">As a result, strings that differ only in character casing are considered to be unique.</span></span>

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

### <span data-ttu-id="93ecc-223">-Wait</span><span class="sxs-lookup"><span data-stu-id="93ecc-223">-Wait</span></span>

<span data-ttu-id="93ecc-224">Indica que o cmdlet desativa a otimização.</span><span class="sxs-lookup"><span data-stu-id="93ecc-224">Indicates that the cmdlet turns off optimization.</span></span> <span data-ttu-id="93ecc-225">O PowerShell executa comandos na ordem em que aparecem no pipeline de comando e permite que eles gerem todos os objetos.</span><span class="sxs-lookup"><span data-stu-id="93ecc-225">PowerShell runs commands in the order that they appear in the command pipeline and lets them generate all objects.</span></span> <span data-ttu-id="93ecc-226">Por padrão, se você incluir um `Select-Object` comando com os parâmetros **First** ou **index** em um pipeline de comando, o PowerShell interromperá o comando que gera os objetos assim que o número selecionado de objetos for gerado.</span><span class="sxs-lookup"><span data-stu-id="93ecc-226">By default, if you include a `Select-Object` command with the **First** or **Index** parameters in a command pipeline, PowerShell stops the command that generates the objects as soon as the selected number of objects is generated.</span></span>

<span data-ttu-id="93ecc-227">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="93ecc-227">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultParameter, IndexParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93ecc-228">-SkipIndex</span><span class="sxs-lookup"><span data-stu-id="93ecc-228">-SkipIndex</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: SkipIndexParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93ecc-229">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="93ecc-229">CommonParameters</span></span>

<span data-ttu-id="93ecc-230">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="93ecc-230">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="93ecc-231">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="93ecc-231">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="93ecc-232">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="93ecc-232">INPUTS</span></span>

### <span data-ttu-id="93ecc-233">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="93ecc-233">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="93ecc-234">Você pode canalizar qualquer objeto para `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="93ecc-234">You can pipe any object to `Select-Object`.</span></span>

## <span data-ttu-id="93ecc-235">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="93ecc-235">OUTPUTS</span></span>

### <span data-ttu-id="93ecc-236">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="93ecc-236">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="93ecc-237">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="93ecc-237">NOTES</span></span>

- <span data-ttu-id="93ecc-238">Você também pode se referir ao `Select-Object` cmdlet por seu alias interno, `select` .</span><span class="sxs-lookup"><span data-stu-id="93ecc-238">You can also refer to the `Select-Object` cmdlet by its built-in alias, `select`.</span></span> <span data-ttu-id="93ecc-239">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="93ecc-239">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

- <span data-ttu-id="93ecc-240">O recurso de otimização do `Select-Object` está disponível apenas para comandos que gravam objetos no pipeline conforme eles são processados.</span><span class="sxs-lookup"><span data-stu-id="93ecc-240">The optimization feature of `Select-Object` is available only for commands that write objects to the pipeline as they are processed.</span></span> <span data-ttu-id="93ecc-241">Esse recurso não tem nenhum efeito em comandos que armazenam objetos processados em buffer e gravam-nos como uma coleção de comandos.</span><span class="sxs-lookup"><span data-stu-id="93ecc-241">It has no effect on commands that buffer processed objects and write them as a collection.</span></span> <span data-ttu-id="93ecc-242">Gravar objetos imediatamente é uma prática recomendada para design de cmdlets.</span><span class="sxs-lookup"><span data-stu-id="93ecc-242">Writing objects immediately is a cmdlet design best practice.</span></span> <span data-ttu-id="93ecc-243">Para obter mais informações, consulte _gravar registros únicos no pipeline_ em [diretrizes de desenvolvimento altamente incentivadas](/powershell/scripting/developer/windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="93ecc-243">For more information, see _Write Single Records to the Pipeline_ in [Strongly Encouraged Development Guidelines](/powershell/scripting/developer/windows-powershell).</span></span>

## <span data-ttu-id="93ecc-244">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="93ecc-244">RELATED LINKS</span></span>

[<span data-ttu-id="93ecc-245">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="93ecc-245">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="93ecc-246">Group-Object</span><span class="sxs-lookup"><span data-stu-id="93ecc-246">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="93ecc-247">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="93ecc-247">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="93ecc-248">Where-Object</span><span class="sxs-lookup"><span data-stu-id="93ecc-248">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
