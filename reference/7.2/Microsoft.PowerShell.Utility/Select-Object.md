---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/select-object?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Select-Object
ms.openlocfilehash: 80882d27c9c8fa2d7f9e1c8ca00a02cf73ae94e6
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597181"
---
# <span data-ttu-id="d522b-102">Select-Object</span><span class="sxs-lookup"><span data-stu-id="d522b-102">Select-Object</span></span>

## <span data-ttu-id="d522b-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d522b-103">SYNOPSIS</span></span>
<span data-ttu-id="d522b-104">Seleciona objetos ou propriedades de objeto.</span><span class="sxs-lookup"><span data-stu-id="d522b-104">Selects objects or object properties.</span></span>

## <span data-ttu-id="d522b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d522b-105">SYNTAX</span></span>

### <span data-ttu-id="d522b-106">Defaultparameter (padrão)</span><span class="sxs-lookup"><span data-stu-id="d522b-106">DefaultParameter (Default)</span></span>

```
Select-Object [-InputObject <PSObject>] [[-Property] <Object[]>] [-ExcludeProperty <String[]>]
 [-ExpandProperty <String>] [-Unique] [-Last <Int32>] [-First <Int32>] [-Skip <Int32>] [-Wait]
 [<CommonParameters>]
```

### <span data-ttu-id="d522b-107">SkipLastParameter</span><span class="sxs-lookup"><span data-stu-id="d522b-107">SkipLastParameter</span></span>

```
Select-Object [-InputObject <PSObject>] [[-Property] <Object[]>] [-ExcludeProperty <String[]>]
 [-ExpandProperty <String>] [-Unique] [-SkipLast <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="d522b-108">IndexParameter</span><span class="sxs-lookup"><span data-stu-id="d522b-108">IndexParameter</span></span>

```
Select-Object [-InputObject <PSObject>] [-Unique] [-Wait] [-Index <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="d522b-109">SkipIndexParameter</span><span class="sxs-lookup"><span data-stu-id="d522b-109">SkipIndexParameter</span></span>

```
Select-Object [-InputObject <PSObject>] [-Unique] [-SkipIndex <Int32[]>] [<CommonParameters>]
```

## <span data-ttu-id="d522b-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d522b-110">DESCRIPTION</span></span>

<span data-ttu-id="d522b-111">O `Select-Object` cmdlet seleciona as propriedades especificadas de um objeto ou conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="d522b-111">The `Select-Object` cmdlet selects specified properties of an object or set of objects.</span></span> <span data-ttu-id="d522b-112">Ele também pode selecionar objetos únicos, um número especificado de objetos, ou então objetos em uma posição especificada em uma matriz.</span><span class="sxs-lookup"><span data-stu-id="d522b-112">It can also select unique objects, a specified number of objects, or objects in a specified position in an array.</span></span>

<span data-ttu-id="d522b-113">Para selecionar objetos de uma coleção, use os parâmetros **First**, **Last**, **Unique**, **Skip** e **Index**.</span><span class="sxs-lookup"><span data-stu-id="d522b-113">To select objects from a collection, use the **First**, **Last**, **Unique**, **Skip**, and **Index** parameters.</span></span> <span data-ttu-id="d522b-114">Para selecionar as propriedades do objeto, use o parâmetro **Property**.</span><span class="sxs-lookup"><span data-stu-id="d522b-114">To select object properties, use the **Property** parameter.</span></span> <span data-ttu-id="d522b-115">Quando você seleciona propriedades, o `Select-Object` retorna novos objetos que têm apenas as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="d522b-115">When you select properties, `Select-Object` returns new objects that have only the specified properties.</span></span>

<span data-ttu-id="d522b-116">A partir do Windows PowerShell 3,0, `Select-Object` o inclui um recurso de otimização que impede que os comandos criem e processem objetos que não são usados.</span><span class="sxs-lookup"><span data-stu-id="d522b-116">Beginning in Windows PowerShell 3.0, `Select-Object` includes an optimization feature that prevents commands from creating and processing objects that are not used.</span></span>

<span data-ttu-id="d522b-117">Quando você inclui um `Select-Object` comando com os parâmetros **First** ou **index** em um pipeline de comando, o PowerShell interrompe o comando que gera os objetos assim que o número selecionado de objetos é gerado, mesmo quando o comando que gera os objetos é exibido antes do `Select-Object` comando no pipeline.</span><span class="sxs-lookup"><span data-stu-id="d522b-117">When you include a `Select-Object` command with the **First** or **Index** parameters in a command pipeline, PowerShell stops the command that generates the objects as soon as the selected number of objects is generated, even when the command that generates the objects appears before the `Select-Object` command in the pipeline.</span></span> <span data-ttu-id="d522b-118">Para desativar esse comportamento de otimização, use o parâmetro **Wait**.</span><span class="sxs-lookup"><span data-stu-id="d522b-118">To turn off this optimizing behavior, use the **Wait** parameter.</span></span>

## <span data-ttu-id="d522b-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d522b-119">EXAMPLES</span></span>

### <span data-ttu-id="d522b-120">Exemplo 1: selecionar objetos por Propriedade</span><span class="sxs-lookup"><span data-stu-id="d522b-120">Example 1: Select objects by property</span></span>

<span data-ttu-id="d522b-121">Este exemplo cria objetos que têm as propriedades de **nome**, **ID** e conjunto de trabalho (**WS**) de objetos de processo.</span><span class="sxs-lookup"><span data-stu-id="d522b-121">This example creates objects that have the **Name**, **ID**, and working set (**WS**) properties of process objects.</span></span>

```powershell
Get-Process | Select-Object -Property ProcessName, Id, WS
```

### <span data-ttu-id="d522b-122">Exemplo 2: selecionar objetos por propriedade e formatar os resultados</span><span class="sxs-lookup"><span data-stu-id="d522b-122">Example 2: Select objects by property and format the results</span></span>

<span data-ttu-id="d522b-123">Este exemplo obtém informações sobre os módulos usados pelos processos no computador.</span><span class="sxs-lookup"><span data-stu-id="d522b-123">This example gets information about the modules used by the processes on the computer.</span></span> <span data-ttu-id="d522b-124">Ele usa `Get-Process` o cmdlet para obter o processo no computador.</span><span class="sxs-lookup"><span data-stu-id="d522b-124">It uses `Get-Process` cmdlet to get the process on the computer.</span></span>

<span data-ttu-id="d522b-125">Ele usa o `Select-Object` cmdlet para gerar uma matriz de `[System.Diagnostics.ProcessModule]` instâncias, conforme contido na propriedade **modules** de cada `System.Diagnostics.Process` saída de instância por `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="d522b-125">It uses the `Select-Object` cmdlet to output an array of `[System.Diagnostics.ProcessModule]` instances as contained in the **Modules** property of each `System.Diagnostics.Process` instance output by `Get-Process`.</span></span>

<span data-ttu-id="d522b-126">O parâmetro **Property** do `Select-Object` cmdlet seleciona os nomes dos processos.</span><span class="sxs-lookup"><span data-stu-id="d522b-126">The **Property** parameter of the `Select-Object` cmdlet selects the process names.</span></span> <span data-ttu-id="d522b-127">Isso adiciona uma `ProcessName` **notaproperty** a cada `[System.Diagnostics.ProcessModule]` instância e a popula com o valor da propriedade **ProcessName** do processo atual.</span><span class="sxs-lookup"><span data-stu-id="d522b-127">This adds a `ProcessName` **NoteProperty** to every `[System.Diagnostics.ProcessModule]` instance and populates it with the value of current process's **ProcessName** property.</span></span>

<span data-ttu-id="d522b-128">Por fim, `Format-List` o cmdlet é usado para exibir o nome e os módulos de cada processo em uma lista.</span><span class="sxs-lookup"><span data-stu-id="d522b-128">Finally, `Format-List` cmdlet is used to display the name and modules of each process in a list.</span></span>

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

### <span data-ttu-id="d522b-129">Exemplo 3: selecionar processos usando a maior parte da memória</span><span class="sxs-lookup"><span data-stu-id="d522b-129">Example 3: Select processes using the most memory</span></span>

<span data-ttu-id="d522b-130">Este exemplo obtém os cinco processos que estão usando a maior parte da memória.</span><span class="sxs-lookup"><span data-stu-id="d522b-130">This example gets the five processes that are using the most memory.</span></span> <span data-ttu-id="d522b-131">O `Get-Process` cmdlet obtém os processos no computador.</span><span class="sxs-lookup"><span data-stu-id="d522b-131">The `Get-Process` cmdlet gets the processes on the computer.</span></span> <span data-ttu-id="d522b-132">O `Sort-Object` cmdlet classifica os processos de acordo com o uso de memória (conjunto de trabalho) e o `Select-Object` cmdlet seleciona apenas os últimos cinco membros da matriz de objetos resultante.</span><span class="sxs-lookup"><span data-stu-id="d522b-132">The `Sort-Object` cmdlet sorts the processes according to memory (working set) usage, and the `Select-Object` cmdlet selects only the last five members of the resulting array of objects.</span></span>

<span data-ttu-id="d522b-133">O parâmetro **Wait** não é necessário em comandos que incluem o `Sort-Object` cmdlet porque o `Sort-Object` processa todos os objetos e, em seguida, retorna uma coleção.</span><span class="sxs-lookup"><span data-stu-id="d522b-133">The **Wait** parameter is not required in commands that include the `Sort-Object` cmdlet because `Sort-Object` processes all objects and then returns a collection.</span></span> <span data-ttu-id="d522b-134">A `Select-Object` otimização está disponível apenas para comandos que retornam objetos individualmente à medida que são processados.</span><span class="sxs-lookup"><span data-stu-id="d522b-134">The `Select-Object` optimization is available only for commands that return objects individually as they are processed.</span></span>

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

### <span data-ttu-id="d522b-135">Exemplo 4: selecionar caracteres exclusivos de uma matriz</span><span class="sxs-lookup"><span data-stu-id="d522b-135">Example 4: Select unique characters from an array</span></span>

<span data-ttu-id="d522b-136">Este exemplo usa o parâmetro **exclusivo** de `Select-Object` para obter caracteres exclusivos de uma matriz de caracteres.</span><span class="sxs-lookup"><span data-stu-id="d522b-136">This example uses the **Unique** parameter of `Select-Object` to get unique characters from an array of characters.</span></span>

```powershell
"a","b","c","a","a","a" | Select-Object -Unique
```

```Output
a
b
c
```

### <span data-ttu-id="d522b-137">Exemplo 5: selecionar eventos mais recentes e mais antigos no log de eventos</span><span class="sxs-lookup"><span data-stu-id="d522b-137">Example 5: Select newest and oldest events in the event log</span></span>

<span data-ttu-id="d522b-138">Este exemplo obtém os primeiros (mais recentes) e os últimos eventos (mais antigos) no log de eventos do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d522b-138">This example gets the first (newest) and last (oldest) events in the Windows PowerShell event log.</span></span>

<span data-ttu-id="d522b-139">`Get-EventLog` Obtém todos os eventos no log do Windows PowerShell e os salva na `$a` variável.</span><span class="sxs-lookup"><span data-stu-id="d522b-139">`Get-EventLog` gets all events in the Windows PowerShell log and saves them in the `$a` variable.</span></span>
<span data-ttu-id="d522b-140">Em seguida, `$a` é canalizado para o `Select-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d522b-140">Then, `$a` is piped to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="d522b-141">O `Select-Object` comando usa o parâmetro **index** para selecionar eventos da matriz de eventos na `$a` variável.</span><span class="sxs-lookup"><span data-stu-id="d522b-141">The `Select-Object` command uses the **Index** parameter to select events from the array of events in the `$a` variable.</span></span> <span data-ttu-id="d522b-142">O índice do primeiro evento é 0.</span><span class="sxs-lookup"><span data-stu-id="d522b-142">The index of the first event is 0.</span></span> <span data-ttu-id="d522b-143">O índice do último evento é o número de itens em `$a` menos 1.</span><span class="sxs-lookup"><span data-stu-id="d522b-143">The index of the last event is the number of items in `$a` minus 1.</span></span>

```powershell
$a = Get-EventLog -LogName "Windows PowerShell"
$a | Select-Object -Index 0, ($A.count - 1)
```

### <span data-ttu-id="d522b-144">Exemplo 6: selecionar tudo, exceto o primeiro objeto</span><span class="sxs-lookup"><span data-stu-id="d522b-144">Example 6: Select all but the first object</span></span>

<span data-ttu-id="d522b-145">Este exemplo cria uma nova PSSession em cada um dos computadores listados na Servers.txt arquivos, exceto para o primeiro.</span><span class="sxs-lookup"><span data-stu-id="d522b-145">This example creates a new PSSession on each of the computers listed in the Servers.txt files, except for the first one.</span></span>

<span data-ttu-id="d522b-146">`Select-Object` seleciona tudo, exceto o primeiro computador em uma lista de nomes de computador.</span><span class="sxs-lookup"><span data-stu-id="d522b-146">`Select-Object` selects all but the first computer in a list of computer names.</span></span> <span data-ttu-id="d522b-147">A lista de computadores resultante é definida como o valor do parâmetro **ComputerName** do `New-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d522b-147">The resulting list of computers is set as the value of the **ComputerName** parameter of the `New-PSSession` cmdlet.</span></span>

```powershell
New-PSSession -ComputerName (Get-Content Servers.txt | Select-Object -Skip 1)
```

### <span data-ttu-id="d522b-148">Exemplo 7: renomear arquivos e selecionar vários para revisão</span><span class="sxs-lookup"><span data-stu-id="d522b-148">Example 7: Rename files and select several to review</span></span>

<span data-ttu-id="d522b-149">Este exemplo adiciona um sufixo "-ro" aos nomes base dos arquivos de texto que têm o atributo somente leitura e, em seguida, exibe os cinco primeiros arquivos para que o usuário possa ver uma amostra do efeito.</span><span class="sxs-lookup"><span data-stu-id="d522b-149">This example adds a "-ro" suffix to the base names of text files that have the read-only attribute and then displays the first five files so the user can see a sample of the effect.</span></span>

<span data-ttu-id="d522b-150">`Get-ChildItem` usa o parâmetro dinâmico **ReadOnly** para obter arquivos somente leitura.</span><span class="sxs-lookup"><span data-stu-id="d522b-150">`Get-ChildItem` uses the **ReadOnly** dynamic parameter to get read-only files.</span></span> <span data-ttu-id="d522b-151">Os arquivos resultantes são canalizados para o `Rename-Item` cmdlet, que renomeia o arquivo.</span><span class="sxs-lookup"><span data-stu-id="d522b-151">The resulting files are piped to the `Rename-Item` cmdlet, which renames the file.</span></span> <span data-ttu-id="d522b-152">Ele usa o parâmetro **PassThru** do `Rename-Item` para enviar os arquivos renomeados para o `Select-Object` cmdlet, que seleciona os primeiros 5 para exibição.</span><span class="sxs-lookup"><span data-stu-id="d522b-152">It uses the **Passthru** parameter of `Rename-Item` to send the renamed files to the `Select-Object` cmdlet, which selects the first 5 for display.</span></span>

<span data-ttu-id="d522b-153">O parâmetro **Wait** de `Select-Object` impede que o PowerShell interrompa o `Get-ChildItem` cmdlet depois de obter os primeiros cinco arquivos de texto somente leitura.</span><span class="sxs-lookup"><span data-stu-id="d522b-153">The **Wait** parameter of `Select-Object` prevents PowerShell from stopping the `Get-ChildItem` cmdlet after it gets the first five read-only text files.</span></span> <span data-ttu-id="d522b-154">Sem este parâmetro, somente os primeiros cinco arquivos somente leitura devem ser renomeados.</span><span class="sxs-lookup"><span data-stu-id="d522b-154">Without this parameter, only the first five read-only files would be renamed.</span></span>

```powershell
Get-ChildItem *.txt -ReadOnly |
    Rename-Item -NewName {$_.BaseName + "-ro.txt"} -PassThru |
    Select-Object -First 5 -Wait
```

### <span data-ttu-id="d522b-155">Exemplo 8: demonstrar as complexidades do parâmetro-ExpandProperty</span><span class="sxs-lookup"><span data-stu-id="d522b-155">Example 8: Demonstrate the intricacies of the -ExpandProperty parameter</span></span>

<span data-ttu-id="d522b-156">Este exemplo demonstra as complexidades do parâmetro **ExpandProperty** .</span><span class="sxs-lookup"><span data-stu-id="d522b-156">This example demonstrates the intricacies of the **ExpandProperty** parameter.</span></span>

<span data-ttu-id="d522b-157">Observe que a saída gerada foi uma matriz de `[System.Int32]` instâncias.</span><span class="sxs-lookup"><span data-stu-id="d522b-157">Note that the output generated was an array of `[System.Int32]` instances.</span></span> <span data-ttu-id="d522b-158">As instâncias estão em conformidade com as regras de formatação padrão da **exibição de saída**.</span><span class="sxs-lookup"><span data-stu-id="d522b-158">The instances conform to standard formatting rules of the **Output View**.</span></span> <span data-ttu-id="d522b-159">Isso é verdadeiro para todas as propriedades *expandidas* .</span><span class="sxs-lookup"><span data-stu-id="d522b-159">This is true for any *Expanded* properties.</span></span> <span data-ttu-id="d522b-160">Se os objetos enviados tiverem um formato padrão específico, a propriedade expandida poderá não estar visível.</span><span class="sxs-lookup"><span data-stu-id="d522b-160">If the outputted objects have a specific standard format, the expanded property might not be visible.</span></span>

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

### <span data-ttu-id="d522b-161">Exemplo 9: criar propriedades personalizadas em objetos</span><span class="sxs-lookup"><span data-stu-id="d522b-161">Example 9: Create custom properties on objects</span></span>

<span data-ttu-id="d522b-162">O exemplo a seguir demonstra `Select-Object` como usar o para adicionar uma propriedade personalizada a qualquer objeto.</span><span class="sxs-lookup"><span data-stu-id="d522b-162">The following example demonstrates using `Select-Object` to add a custom property to any object.</span></span>
<span data-ttu-id="d522b-163">Quando você especifica um nome de propriedade que não existe, o `Select-Object` cria essa propriedade como uma **observaçãoproperty** em cada objeto passado.</span><span class="sxs-lookup"><span data-stu-id="d522b-163">When you specify a property name that does not exist, `Select-Object` creates that property as a **NoteProperty** on each object passed.</span></span>

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

### <span data-ttu-id="d522b-164">Exemplo 10: criar propriedades calculadas para cada InputObject</span><span class="sxs-lookup"><span data-stu-id="d522b-164">Example 10: Create calculated properties for each InputObject</span></span>

<span data-ttu-id="d522b-165">Este exemplo demonstra `Select-Object` como usar o para adicionar propriedades calculadas à sua entrada.</span><span class="sxs-lookup"><span data-stu-id="d522b-165">This example demonstrates using `Select-Object` to add calculated properties to your input.</span></span> <span data-ttu-id="d522b-166">Passar um **scriptblock** para o parâmetro **Property** faz com que o `Select-Object` avalie a expressão em cada objeto passado e adicione os resultados à saída.</span><span class="sxs-lookup"><span data-stu-id="d522b-166">Passing a **ScriptBlock** to the **Property** parameter causes `Select-Object` to evaluate the expression on each object passed and add the results to the output.</span></span> <span data-ttu-id="d522b-167">Dentro do **scriptblock**, você pode usar a `$_` variável para fazer referência ao objeto atual no pipeline.</span><span class="sxs-lookup"><span data-stu-id="d522b-167">Within the **ScriptBlock**, you can use the `$_` variable to reference the current object in the pipeline.</span></span>

<span data-ttu-id="d522b-168">Por padrão, `Select-Object` o usará a cadeia de **scriptblock** como o nome da propriedade.</span><span class="sxs-lookup"><span data-stu-id="d522b-168">By default, `Select-Object` will use the **ScriptBlock** string as the name of the property.</span></span> <span data-ttu-id="d522b-169">Usando uma **tabela de hash**, você pode rotular a saída do **scriptblock** como uma propriedade personalizada adicionada a cada objeto.</span><span class="sxs-lookup"><span data-stu-id="d522b-169">Using a **Hashtable**, you can label the output of your **ScriptBlock** as a custom property added to each object.</span></span> <span data-ttu-id="d522b-170">Você pode adicionar várias propriedades calculadas a cada objeto passado para `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="d522b-170">You can add multiple calculated properties to each object passed to `Select-Object`.</span></span>

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

## <span data-ttu-id="d522b-171">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d522b-171">PARAMETERS</span></span>

### <span data-ttu-id="d522b-172">-ExcludeProperty</span><span class="sxs-lookup"><span data-stu-id="d522b-172">-ExcludeProperty</span></span>

<span data-ttu-id="d522b-173">Especifica as propriedades que esse cmdlet exclui da operação.</span><span class="sxs-lookup"><span data-stu-id="d522b-173">Specifies the properties that this cmdlet excludes from the operation.</span></span> <span data-ttu-id="d522b-174">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="d522b-174">Wildcards are permitted.</span></span>

<span data-ttu-id="d522b-175">A partir do PowerShell 6, não é mais necessário incluir o parâmetro **Property** para que o **ExcludeProperty** funcione.</span><span class="sxs-lookup"><span data-stu-id="d522b-175">Beginning in PowerShell 6, it is no longer required to include the **Property** parameter for **ExcludeProperty** to work.</span></span>

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

### <span data-ttu-id="d522b-176">-ExpandProperty</span><span class="sxs-lookup"><span data-stu-id="d522b-176">-ExpandProperty</span></span>

<span data-ttu-id="d522b-177">Especifica uma propriedade a selecionar e indica que deve-se tentar expandir essa propriedade.</span><span class="sxs-lookup"><span data-stu-id="d522b-177">Specifies a property to select, and indicates that an attempt should be made to expand that property.</span></span>

- <span data-ttu-id="d522b-178">Se a propriedade especificada for uma matriz, cada valor da matriz será incluído na saída.</span><span class="sxs-lookup"><span data-stu-id="d522b-178">If the specified property is an array, each value of the array is included in the output.</span></span>
- <span data-ttu-id="d522b-179">Se a propriedade especificada for um objeto, as propriedades de objetos serão expandidas para cada **InputObject**</span><span class="sxs-lookup"><span data-stu-id="d522b-179">If the specified property is an object, the objects properties are expanded for every **InputObject**</span></span>

<span data-ttu-id="d522b-180">Em ambos os casos, o **tipo** de saída de objetos corresponderá ao **tipo** da propriedade expandida.</span><span class="sxs-lookup"><span data-stu-id="d522b-180">In either case, the **Type** of objects output will match the **Type** of the expanded property.</span></span>

<span data-ttu-id="d522b-181">Se o parâmetro **Property** for especificado, o `Select-Object` tentará adicionar cada propriedade selecionada como uma **NoteProperty** a cada objeto de saída.</span><span class="sxs-lookup"><span data-stu-id="d522b-181">If the **Property** parameter is specified, `Select-Object` will attempt to add each selected property as a **NoteProperty** to every outputted object.</span></span>

> [!WARNING]
> <span data-ttu-id="d522b-182">Se você receber o erro: SELECT: a propriedade não pode ser processada porque `<PropertyName>` a propriedade já existe, considere o seguinte.</span><span class="sxs-lookup"><span data-stu-id="d522b-182">If you receive the error: Select : Property cannot be processed because property `<PropertyName>` already exists, consider the following.</span></span>
> <span data-ttu-id="d522b-183">Observe que, ao `-ExpandProperty` usar `Select-Object` o, não é possível substituir uma propriedade existente.</span><span class="sxs-lookup"><span data-stu-id="d522b-183">Note that when using `-ExpandProperty`, `Select-Object` can not replace an existing property.</span></span>
> <span data-ttu-id="d522b-184">Isso significa:</span><span class="sxs-lookup"><span data-stu-id="d522b-184">This means:</span></span>
>
> - <span data-ttu-id="d522b-185">Se o objeto expandido tiver uma propriedade de mesmo nome, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="d522b-185">If the expanded object has a property of the same name, an error will occur.</span></span>
> - <span data-ttu-id="d522b-186">Se o objeto *selecionado* tiver uma propriedade de mesmo nome que uma propriedade de objetos *expandida* , ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="d522b-186">If the *Selected* object has a property of the same name as an *Expanded* objects property, an error will occur.</span></span>

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

### <span data-ttu-id="d522b-187">-Primeiro</span><span class="sxs-lookup"><span data-stu-id="d522b-187">-First</span></span>

<span data-ttu-id="d522b-188">Especifica o número de objetos a selecionar desde o início de uma matriz de objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="d522b-188">Specifies the number of objects to select from the beginning of an array of input objects.</span></span>

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

### <span data-ttu-id="d522b-189">-Índice</span><span class="sxs-lookup"><span data-stu-id="d522b-189">-Index</span></span>

<span data-ttu-id="d522b-190">Seleciona objetos de uma matriz com base nos valores de índice desses objetos.</span><span class="sxs-lookup"><span data-stu-id="d522b-190">Selects objects from an array based on their index values.</span></span> <span data-ttu-id="d522b-191">Digite os índices separados por vírgulas em uma lista.</span><span class="sxs-lookup"><span data-stu-id="d522b-191">Enter the indexes in a comma-separated list.</span></span> <span data-ttu-id="d522b-192">Os índices em uma matriz começam com 0, onde 0 representa o primeiro valor e (n-1) representa o último valor.</span><span class="sxs-lookup"><span data-stu-id="d522b-192">Indexes in an array begin with 0, where 0 represents the first value and (n-1) represents the last value.</span></span>

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

### <span data-ttu-id="d522b-193">-InputObject</span><span class="sxs-lookup"><span data-stu-id="d522b-193">-InputObject</span></span>

<span data-ttu-id="d522b-194">Especifica os objetos a enviar ao cmdlet pelo pipeline.</span><span class="sxs-lookup"><span data-stu-id="d522b-194">Specifies objects to send to the cmdlet through the pipeline.</span></span> <span data-ttu-id="d522b-195">Esse parâmetro permite canalizar objetos para o `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="d522b-195">This parameter enables you to pipe objects to `Select-Object`.</span></span>

<span data-ttu-id="d522b-196">Quando você passa objetos para o parâmetro **InputObject** , em vez de usar o pipeline, `Select-Object` o trata o **InputObject** como um único objeto, mesmo que o valor seja uma coleção.</span><span class="sxs-lookup"><span data-stu-id="d522b-196">When you pass objects to the **InputObject** parameter, instead of using the pipeline, `Select-Object` treats the **InputObject** as a single object, even if the value is a collection.</span></span> <span data-ttu-id="d522b-197">É recomendável que você use o pipeline ao passar coleções para o `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="d522b-197">It is recommended that you use the pipeline when passing collections to `Select-Object`.</span></span>

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

### <span data-ttu-id="d522b-198">-Último</span><span class="sxs-lookup"><span data-stu-id="d522b-198">-Last</span></span>

<span data-ttu-id="d522b-199">Especifica o número de objetos a selecionar desde o final de uma matriz de objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="d522b-199">Specifies the number of objects to select from the end of an array of input objects.</span></span>

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

### <span data-ttu-id="d522b-200">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="d522b-200">-Property</span></span>

<span data-ttu-id="d522b-201">Especifica as propriedades a selecionar.</span><span class="sxs-lookup"><span data-stu-id="d522b-201">Specifies the properties to select.</span></span> <span data-ttu-id="d522b-202">Essas propriedades são adicionadas como membros da **observaçãoproperty** aos objetos de saída.</span><span class="sxs-lookup"><span data-stu-id="d522b-202">These properties are added as **NoteProperty** members to the output objects.</span></span> <span data-ttu-id="d522b-203">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="d522b-203">Wildcards are permitted.</span></span>

<span data-ttu-id="d522b-204">O valor do parâmetro **Property** pode ser uma nova propriedade calculada.</span><span class="sxs-lookup"><span data-stu-id="d522b-204">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="d522b-205">Para criar uma propriedade calculada, use uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="d522b-205">To create a calculated, property, use a hash table.</span></span>

<span data-ttu-id="d522b-206">As chaves válidas são:</span><span class="sxs-lookup"><span data-stu-id="d522b-206">Valid keys are:</span></span>

- <span data-ttu-id="d522b-207">Nome (ou rótulo)- `<string>`</span><span class="sxs-lookup"><span data-stu-id="d522b-207">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="d522b-208">Expressão- `<string>` ou `<script block>`</span><span class="sxs-lookup"><span data-stu-id="d522b-208">Expression - `<string>` or `<script block>`</span></span>

<span data-ttu-id="d522b-209">Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="d522b-209">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="d522b-210">-Ignorar</span><span class="sxs-lookup"><span data-stu-id="d522b-210">-Skip</span></span>

<span data-ttu-id="d522b-211">Ignora (não seleciona) o número de itens especificado.</span><span class="sxs-lookup"><span data-stu-id="d522b-211">Skips (does not select) the specified number of items.</span></span> <span data-ttu-id="d522b-212">Por padrão, o parâmetro **Skip** conta a partir do início da matriz ou da lista de objetos, mas se o comando usar o **último** parâmetro, ele contará do final da lista ou da matriz.</span><span class="sxs-lookup"><span data-stu-id="d522b-212">By default, the **Skip** parameter counts from the beginning of the array or list of objects, but if the command uses the **Last** parameter, it counts from the end of the list or array.</span></span>

<span data-ttu-id="d522b-213">Ao contrário do parâmetro **Index**, que inicia a contagem em 0, o parâmetro **Skip** começa em 1.</span><span class="sxs-lookup"><span data-stu-id="d522b-213">Unlike the **Index** parameter, which starts counting at 0, the **Skip** parameter begins at 1.</span></span>

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

### <span data-ttu-id="d522b-214">-SkipLast</span><span class="sxs-lookup"><span data-stu-id="d522b-214">-SkipLast</span></span>

<span data-ttu-id="d522b-215">Ignora (não seleciona) o número especificado de itens do final da lista ou da matriz.</span><span class="sxs-lookup"><span data-stu-id="d522b-215">Skips (does not select) the specified number of items from the end of the list or array.</span></span> <span data-ttu-id="d522b-216">Funciona da mesma maneira que o uso de **Skip** junto com o **último** parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d522b-216">Works in the same way as using **Skip** together with **Last** parameter.</span></span>

<span data-ttu-id="d522b-217">Ao contrário do parâmetro de **índice** , que inicia a contagem em 0, o parâmetro **SkipLast** começa em 1.</span><span class="sxs-lookup"><span data-stu-id="d522b-217">Unlike the **Index** parameter, which starts counting at 0, the **SkipLast** parameter begins at 1.</span></span>

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

### <span data-ttu-id="d522b-218">-Exclusivo</span><span class="sxs-lookup"><span data-stu-id="d522b-218">-Unique</span></span>

<span data-ttu-id="d522b-219">Especifica que, se um subconjunto dos objetos de entrada tem valores e propriedades idênticos, apenas um único membro do subconjunto será selecionado.</span><span class="sxs-lookup"><span data-stu-id="d522b-219">Specifies that if a subset of the input objects has identical properties and values, only a single member of the subset will be selected.</span></span>

<span data-ttu-id="d522b-220">Este parâmetro diferencia maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="d522b-220">This parameter is case-sensitive.</span></span> <span data-ttu-id="d522b-221">Como resultado, cadeias de caracteres que diferem apenas em maiúsculas e minúsculas são consideradas como sendo exclusivas.</span><span class="sxs-lookup"><span data-stu-id="d522b-221">As a result, strings that differ only in character casing are considered to be unique.</span></span>

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

### <span data-ttu-id="d522b-222">-Wait</span><span class="sxs-lookup"><span data-stu-id="d522b-222">-Wait</span></span>

<span data-ttu-id="d522b-223">Indica que o cmdlet desativa a otimização.</span><span class="sxs-lookup"><span data-stu-id="d522b-223">Indicates that the cmdlet turns off optimization.</span></span> <span data-ttu-id="d522b-224">O PowerShell executa comandos na ordem em que aparecem no pipeline de comando e permite que eles gerem todos os objetos.</span><span class="sxs-lookup"><span data-stu-id="d522b-224">PowerShell runs commands in the order that they appear in the command pipeline and lets them generate all objects.</span></span> <span data-ttu-id="d522b-225">Por padrão, se você incluir um `Select-Object` comando com os parâmetros **First** ou **index** em um pipeline de comando, o PowerShell interromperá o comando que gera os objetos assim que o número selecionado de objetos for gerado.</span><span class="sxs-lookup"><span data-stu-id="d522b-225">By default, if you include a `Select-Object` command with the **First** or **Index** parameters in a command pipeline, PowerShell stops the command that generates the objects as soon as the selected number of objects is generated.</span></span>

<span data-ttu-id="d522b-226">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="d522b-226">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="d522b-227">-SkipIndex</span><span class="sxs-lookup"><span data-stu-id="d522b-227">-SkipIndex</span></span>

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

### <span data-ttu-id="d522b-228">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d522b-228">CommonParameters</span></span>

<span data-ttu-id="d522b-229">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d522b-229">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d522b-230">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="d522b-230">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="d522b-231">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d522b-231">INPUTS</span></span>

### <span data-ttu-id="d522b-232">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="d522b-232">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="d522b-233">Você pode canalizar qualquer objeto para `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="d522b-233">You can pipe any object to `Select-Object`.</span></span>

## <span data-ttu-id="d522b-234">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d522b-234">OUTPUTS</span></span>

### <span data-ttu-id="d522b-235">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="d522b-235">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="d522b-236">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d522b-236">NOTES</span></span>

- <span data-ttu-id="d522b-237">Você também pode se referir ao `Select-Object` cmdlet por seu alias interno, `select` .</span><span class="sxs-lookup"><span data-stu-id="d522b-237">You can also refer to the `Select-Object` cmdlet by its built-in alias, `select`.</span></span> <span data-ttu-id="d522b-238">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="d522b-238">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

- <span data-ttu-id="d522b-239">O recurso de otimização do `Select-Object` está disponível apenas para comandos que gravam objetos no pipeline conforme eles são processados.</span><span class="sxs-lookup"><span data-stu-id="d522b-239">The optimization feature of `Select-Object` is available only for commands that write objects to the pipeline as they are processed.</span></span> <span data-ttu-id="d522b-240">Esse recurso não tem nenhum efeito em comandos que armazenam objetos processados em buffer e gravam-nos como uma coleção de comandos.</span><span class="sxs-lookup"><span data-stu-id="d522b-240">It has no effect on commands that buffer processed objects and write them as a collection.</span></span> <span data-ttu-id="d522b-241">Gravar objetos imediatamente é uma prática recomendada para design de cmdlets.</span><span class="sxs-lookup"><span data-stu-id="d522b-241">Writing objects immediately is a cmdlet design best practice.</span></span> <span data-ttu-id="d522b-242">Para obter mais informações, consulte _gravar registros únicos no pipeline_ em [diretrizes de desenvolvimento altamente incentivadas](/powershell/scripting/developer/windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="d522b-242">For more information, see _Write Single Records to the Pipeline_ in [Strongly Encouraged Development Guidelines](/powershell/scripting/developer/windows-powershell).</span></span>

## <span data-ttu-id="d522b-243">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d522b-243">RELATED LINKS</span></span>

[<span data-ttu-id="d522b-244">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="d522b-244">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="d522b-245">Group-Object</span><span class="sxs-lookup"><span data-stu-id="d522b-245">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="d522b-246">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="d522b-246">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="d522b-247">Where-Object</span><span class="sxs-lookup"><span data-stu-id="d522b-247">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
