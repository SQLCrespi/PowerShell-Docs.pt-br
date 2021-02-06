---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/measure-object?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Measure-Object
ms.openlocfilehash: 594837b2f85f4d5d5d4125d3f7c63ad2c8a16153
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598645"
---
# <span data-ttu-id="150f5-102">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="150f5-102">Measure-Object</span></span>

## <span data-ttu-id="150f5-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="150f5-103">SYNOPSIS</span></span>
<span data-ttu-id="150f5-104">Calcula as propriedades numéricas de objetos e os caracteres, palavras e linhas em objetos de cadeia de caracteres, como arquivos de texto.</span><span class="sxs-lookup"><span data-stu-id="150f5-104">Calculates the numeric properties of objects, and the characters, words, and lines in string objects, such as files of text.</span></span>

## <span data-ttu-id="150f5-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="150f5-105">SYNTAX</span></span>

### <span data-ttu-id="150f5-106">GenericMeasure (padrão)</span><span class="sxs-lookup"><span data-stu-id="150f5-106">GenericMeasure (Default)</span></span>

```
Measure-Object [[-Property] <PSPropertyExpression[]>] [-InputObject <PSObject>] [-StandardDeviation]
 [-Sum] [-AllStats] [-Average] [-Maximum] [-Minimum] [<CommonParameters>]
```

### <span data-ttu-id="150f5-107">Textmeasure</span><span class="sxs-lookup"><span data-stu-id="150f5-107">TextMeasure</span></span>

```
Measure-Object [[-Property] <PSPropertyExpression[]>] [-InputObject <PSObject>] [-Line] [-Word]
 [-Character] [-IgnoreWhiteSpace] [<CommonParameters>]
```

## <span data-ttu-id="150f5-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="150f5-108">DESCRIPTION</span></span>

<span data-ttu-id="150f5-109">O `Measure-Object` cmdlet calcula os valores de propriedade de determinados tipos de objeto.</span><span class="sxs-lookup"><span data-stu-id="150f5-109">The `Measure-Object` cmdlet calculates the property values of certain types of object.</span></span>
<span data-ttu-id="150f5-110">`Measure-Object` executa três tipos de medidas, dependendo dos parâmetros no comando.</span><span class="sxs-lookup"><span data-stu-id="150f5-110">`Measure-Object` performs three types of measurements, depending on the parameters in the command.</span></span>

<span data-ttu-id="150f5-111">O `Measure-Object` cmdlet executa cálculos nos valores de propriedade de objetos.</span><span class="sxs-lookup"><span data-stu-id="150f5-111">The `Measure-Object` cmdlet performs calculations on the property values of objects.</span></span> <span data-ttu-id="150f5-112">Você pode usar `Measure-Object` para contar objetos ou contar objetos com uma **Propriedade** especificada.</span><span class="sxs-lookup"><span data-stu-id="150f5-112">You can use `Measure-Object` to count objects or count objects with a specified **Property**.</span></span> <span data-ttu-id="150f5-113">Você também pode usar `Measure-Object` para calcular o **mínimo**, **máximo**, **soma**, **i** e **média** de valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="150f5-113">You can also use `Measure-Object` to calculate the **Minimum**, **Maximum**, **Sum**, **StandardDeviation** and **Average** of numeric values.</span></span> <span data-ttu-id="150f5-114">Para objetos de **cadeia de caracteres** , você também pode usar `Measure-Object` para contar o número de linhas, palavras e caracteres.</span><span class="sxs-lookup"><span data-stu-id="150f5-114">For **String** objects, you can also use `Measure-Object` to count the number of lines, words, and characters.</span></span>

## <span data-ttu-id="150f5-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="150f5-115">EXAMPLES</span></span>

### <span data-ttu-id="150f5-116">Exemplo 1: contar os arquivos e as pastas em um diretório</span><span class="sxs-lookup"><span data-stu-id="150f5-116">Example 1: Count the files and folders in a directory</span></span>

<span data-ttu-id="150f5-117">Esse comando conta os arquivos e pastas no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="150f5-117">This command counts the files and folders in the current directory.</span></span>

```powershell
Get-ChildItem | Measure-Object
```

### <span data-ttu-id="150f5-118">Exemplo 2: medir os arquivos em um diretório</span><span class="sxs-lookup"><span data-stu-id="150f5-118">Example 2: Measure the files in a directory</span></span>

<span data-ttu-id="150f5-119">Esse comando exibe o **mínimo**, o **máximo** e a **soma** dos tamanhos de todos os arquivos no diretório atual e o tamanho médio de um arquivo no diretório.</span><span class="sxs-lookup"><span data-stu-id="150f5-119">This command displays the **Minimum**, **Maximum**, and **Sum** of the sizes of all files in the current directory, and the average size of a file in the directory.</span></span>

```powershell
Get-ChildItem | Measure-Object -Property length -Minimum -Maximum -Average
```

### <span data-ttu-id="150f5-120">Exemplo 3: medir o texto em um arquivo de texto</span><span class="sxs-lookup"><span data-stu-id="150f5-120">Example 3: Measure text in a text file</span></span>

<span data-ttu-id="150f5-121">Este comando exibe o número de caracteres, palavras e linhas no arquivo Text.txt.</span><span class="sxs-lookup"><span data-stu-id="150f5-121">This command displays the number of characters, words, and lines in the Text.txt file.</span></span>
<span data-ttu-id="150f5-122">Sem o parâmetro **RAW** , `Get-Content` o gera o arquivo como uma matriz de linhas.</span><span class="sxs-lookup"><span data-stu-id="150f5-122">Without the **Raw** parameter, `Get-Content` outputs the file as an array of lines.</span></span>

<span data-ttu-id="150f5-123">O primeiro comando usa `Set-Content` para adicionar um texto padrão a um arquivo.</span><span class="sxs-lookup"><span data-stu-id="150f5-123">The first command uses `Set-Content` to add some default text to a file.</span></span>

```powershell
"One", "Two", "Three", "Four" | Set-Content -Path C:\Temp\tmp.txt
Get-Content C:\Temp\tmp.txt | Measure-Object -Character -Line -Word
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    4     4         15
```

### <span data-ttu-id="150f5-124">Exemplo 4: objetos de medida que contêm uma propriedade especificada</span><span class="sxs-lookup"><span data-stu-id="150f5-124">Example 4: Measure objects containing a specified Property</span></span>

<span data-ttu-id="150f5-125">Este exemplo conta o número de objetos que têm uma propriedade **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="150f5-125">This example counts the number of objects that have a **DisplayName** property.</span></span> <span data-ttu-id="150f5-126">Os dois primeiros comandos recuperam todos os serviços e processos no computador local.</span><span class="sxs-lookup"><span data-stu-id="150f5-126">The first two commands retrieve all the services and processes on the local machine.</span></span> <span data-ttu-id="150f5-127">O terceiro comando conta o número combinado de serviços e processos.</span><span class="sxs-lookup"><span data-stu-id="150f5-127">The third command counts the combined number of services and processes.</span></span> <span data-ttu-id="150f5-128">O último comando combina as duas coleções e canaliza o resultado para `Measure-Object` .</span><span class="sxs-lookup"><span data-stu-id="150f5-128">The last command combines the two collections and pipes the result to `Measure-Object`.</span></span>

<span data-ttu-id="150f5-129">O objeto **System. Diagnostics. Process** não tem uma propriedade **DisplayName** e é deixado da contagem final.</span><span class="sxs-lookup"><span data-stu-id="150f5-129">The **System.Diagnostics.Process** object does not have a **DisplayName** property, and is left out of the final count.</span></span>

```powershell
$services = Get-Service
$processes = Get-Process
$services + $processes | Measure-Object
$services + $processes | Measure-Object -Property DisplayName
```

```Output
Count    : 682
Average  :
Sum      :
Maximum  :
Minimum  :
Property :

Count    : 290
Average  :
Sum      :
Maximum  :
Minimum  :
Property : DisplayName
```

### <span data-ttu-id="150f5-130">Exemplo 5: medir o conteúdo de um arquivo CSV</span><span class="sxs-lookup"><span data-stu-id="150f5-130">Example 5: Measure the contents of a CSV file</span></span>

<span data-ttu-id="150f5-131">Este comando calcula os médio anos de serviço dos funcionários de uma empresa.</span><span class="sxs-lookup"><span data-stu-id="150f5-131">This command calculates the average years of service of the employees of a company.</span></span>

<span data-ttu-id="150f5-132">O `ServiceYrs.csv` arquivo é um arquivo CSV que contém o número do funcionário e os anos de serviço de cada funcionário.</span><span class="sxs-lookup"><span data-stu-id="150f5-132">The `ServiceYrs.csv` file is a CSV file that contains the employee number and years of service of each employee.</span></span> <span data-ttu-id="150f5-133">A primeira linha da tabela é uma linha de cabeçalho de **empno**, **anos**.</span><span class="sxs-lookup"><span data-stu-id="150f5-133">The first row in the table is a header row of **EmpNo**, **Years**.</span></span>

<span data-ttu-id="150f5-134">Quando você usa `Import-Csv` o para importar o arquivo, o resultado é um **PSCustomObject** com as propriedades de observação de **empno** e **anos**.</span><span class="sxs-lookup"><span data-stu-id="150f5-134">When you use `Import-Csv` to import the file, the result is a **PSCustomObject** with note properties of **EmpNo** and **Years**.</span></span>
<span data-ttu-id="150f5-135">Você pode usar `Measure-Object` para calcular os valores dessas propriedades, assim como qualquer outra propriedade de um objeto.</span><span class="sxs-lookup"><span data-stu-id="150f5-135">You can use `Measure-Object` to calculate the values of these properties, just like any other property of an object.</span></span>

```powershell
Import-Csv d:\test\serviceyrs.csv | Measure-Object -Property years -Minimum -Maximum -Average
```

### <span data-ttu-id="150f5-136">Exemplo 6: medir valores Boolianos</span><span class="sxs-lookup"><span data-stu-id="150f5-136">Example 6: Measure Boolean values</span></span>

<span data-ttu-id="150f5-137">Este exemplo demonstra como o `Measure-Object` pode medir valores Boolianos.</span><span class="sxs-lookup"><span data-stu-id="150f5-137">This example demonstrates how the `Measure-Object` can measure Boolean values.</span></span>
<span data-ttu-id="150f5-138">Nesse caso, ele usa a propriedade  **booliana** PsIsContainer para medir a incidência de pastas (vs. Files) no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="150f5-138">In this case, it uses the **PSIsContainer** **Boolean** property to measure the incidence of folders (vs. files) in the current directory.</span></span>

```powershell
Get-ChildItem | Measure-Object -Property psiscontainer -Maximum -Sum -Minimum -Average
```

```Output
Count             : 126
Average           : 0.0634920634920635
Sum               : 8
Maximum           : 1
Minimum           : 0
StandardDeviation :
Property          : PSIsContainer
```

### <span data-ttu-id="150f5-139">Exemplo 7: cadeias de caracteres de medida</span><span class="sxs-lookup"><span data-stu-id="150f5-139">Example 7: Measure strings</span></span>

<span data-ttu-id="150f5-140">O exemplo a seguir mede o número de linhas, primeiro uma única cadeia de caracteres e, em seguida, em várias cadeias.</span><span class="sxs-lookup"><span data-stu-id="150f5-140">The following example measures the number of lines, first a single string, then across several strings.</span></span> <span data-ttu-id="150f5-141">O caractere de nova linha <code>\`n</code> separa cadeias de caracteres em várias linhas.</span><span class="sxs-lookup"><span data-stu-id="150f5-141">The newline character <code>\`n</code> separates strings into multiple lines.</span></span>

```powershell
# The newline character `n separates the string into separate lines, as shown in the output.
"One`nTwo`nThree"
"One`nTwo`nThree" | Measure-Object -Line
```

```Output
One
Two
Three


Lines Words Characters Property
----- ----- ---------- --------
    3
```

```powershell
# The first string counts as a single line.
# The second string is separated into two lines by the newline character.
"One", "Two`nThree" | Measure-Object -Line
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    3
```

```powershell
# The Word switch counts the number of words in each InputObject
# Each InputObject is treated as a single line.
"One, Two", "Three", "Four Five" | Measure-Object -Word -Line
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    3     5
```

### <span data-ttu-id="150f5-142">Exemplo 8: medir todos os valores</span><span class="sxs-lookup"><span data-stu-id="150f5-142">Example 8: Measure all the values</span></span>

<span data-ttu-id="150f5-143">A partir do PowerShell 6, o parâmetro **Perstats** de `Measure-Object` permite que você meça todas as estatísticas juntas.</span><span class="sxs-lookup"><span data-stu-id="150f5-143">Beginning in PowerShell 6, the **AllStats** parameter of `Measure-Object` allows you to measure all the statistics together.</span></span>

```powershell
1..5 | Measure-Object -AllStats
```

```output
Count             : 5
Average           : 3
Sum               : 15
Maximum           : 5
Minimum           : 1
StandardDeviation : 1.58113883008419
Property          :
```

### <span data-ttu-id="150f5-144">Exemplo 9: medida usando Propriedades scriptblock</span><span class="sxs-lookup"><span data-stu-id="150f5-144">Example 9: Measure using scriptblock properties</span></span>

<span data-ttu-id="150f5-145">A partir do PowerShell 6, `Measure-Object` dá suporte a propriedades **scriptblock** .</span><span class="sxs-lookup"><span data-stu-id="150f5-145">Beginning in PowerShell 6, `Measure-Object` supports **ScriptBlock** properties.</span></span> <span data-ttu-id="150f5-146">O exemplo a seguir demonstra como usar uma propriedade **scriptblock** para determinar o tamanho, em megabytes, de todos os arquivos em um diretório.</span><span class="sxs-lookup"><span data-stu-id="150f5-146">The following example demonstrates how to use a **ScriptBlock** property to determine the size, in MegaBytes, of all the files in a directory.</span></span>

```powershell
Get-ChildItem | Measure-Object -Sum {$_.Length/1MB}
```

### <span data-ttu-id="150f5-147">Exemplo 10: medir as Hashtables</span><span class="sxs-lookup"><span data-stu-id="150f5-147">Example 10: Measure hashtables</span></span>

<span data-ttu-id="150f5-148">A partir do PowerShell 6, o `Measure-Object` dá suporte à medição de entrada de **Hashtable** .</span><span class="sxs-lookup"><span data-stu-id="150f5-148">Beginning in PowerShell 6, `Measure-Object` supports measurement of **hashtable** input.</span></span> <span data-ttu-id="150f5-149">O exemplo a seguir determina o maior valor para a `num` chave de 3 objetos de **tabela de hash** .</span><span class="sxs-lookup"><span data-stu-id="150f5-149">The following example determines the largest value for the `num` key of 3 **hashtable** objects.</span></span>

```powershell
@{num=3}, @{num=4}, @{num=5} | Measure-Object -Maximum Num
```

```output
Count             : 3
Average           :
Sum               :
Maximum           : 5
Minimum           :
StandardDeviation :
Property          : num
```

### <span data-ttu-id="150f5-150">Exemplo 11: medir o desvio padrão</span><span class="sxs-lookup"><span data-stu-id="150f5-150">Example 11: Measure the Standard Deviation</span></span>

<span data-ttu-id="150f5-151">A partir do PowerShell 6, `Measure-Object` o oferece suporte ao `-StandardDeviation` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="150f5-151">Beginning in PowerShell 6, `Measure-Object` supports the `-StandardDeviation` parameter.</span></span> <span data-ttu-id="150f5-152">O exemplo a seguir determina o *desvio padrão* para a CPU usada por todos os processos.</span><span class="sxs-lookup"><span data-stu-id="150f5-152">The following example determines the *standard deviation* for the CPU used by all processes.</span></span> <span data-ttu-id="150f5-153">Um grande desvio indicaria um pequeno número de processos consumindo a maioria da CPU.</span><span class="sxs-lookup"><span data-stu-id="150f5-153">A large deviation would indicate a small number of processes consuming the most CPU.</span></span>

```powershell
Get-Process | Measure-Object -Average -StandardDeviation CPU
```

```output
Count             : 303
Average           : 163.032384488449
Sum               :
Maximum           :
Minimum           :
StandardDeviation : 859.444048419069
Property          : CPU
```

### <span data-ttu-id="150f5-154">Exemplo 12: medida usando curingas</span><span class="sxs-lookup"><span data-stu-id="150f5-154">Example 12: Measure using wildcards</span></span>

<span data-ttu-id="150f5-155">A partir do PowerShell 6, o `Measure-Object` dá suporte à medição de objetos usando curingas em nomes de propriedade.</span><span class="sxs-lookup"><span data-stu-id="150f5-155">Beginning in PowerShell 6, `Measure-Object` supports measurement of objects by using wildcards in property names.</span></span> <span data-ttu-id="150f5-156">O exemplo a seguir determina o máximo de qualquer tipo de uso de memória paginado entre um conjunto de processos.</span><span class="sxs-lookup"><span data-stu-id="150f5-156">The following example determines the maximum of any type of paged memory usage among a set of processes.</span></span>

```powershell
Get-Process | Measure-Object -Maximum *paged*memory*size
```

```output
Count             : 303
Average           :
Sum               :
Maximum           : 735784
Minimum           :
StandardDeviation :
Property          : NonpagedSystemMemorySize

Count             : 303
Average           :
Sum               :
Maximum           : 352104448
Minimum           :
StandardDeviation :
Property          : PagedMemorySize

Count             : 303
Average           :
Sum               :
Maximum           : 2201968
Minimum           :
StandardDeviation :
Property          : PagedSystemMemorySize

Count             : 303
Average           :
Sum               :
Maximum           : 719032320
Minimum           :
StandardDeviation :
Property          : PeakPagedMemorySize
```

## <span data-ttu-id="150f5-157">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="150f5-157">PARAMETERS</span></span>

### <span data-ttu-id="150f5-158">-Média</span><span class="sxs-lookup"><span data-stu-id="150f5-158">-Average</span></span>

<span data-ttu-id="150f5-159">Indica que o cmdlet exibe o valor médio das propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="150f5-159">Indicates that the cmdlet displays the average value of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="150f5-160">-Caractere</span><span class="sxs-lookup"><span data-stu-id="150f5-160">-Character</span></span>

<span data-ttu-id="150f5-161">Indica que o cmdlet conta o número de caracteres nos objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="150f5-161">Indicates that the cmdlet counts the number of characters in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="150f5-162">As opções de **palavra**, **Char** e **linha** contam *dentro* de cada objeto de entrada, bem como *entre* objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="150f5-162">The **Word**, **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="150f5-163">Consulte o exemplo 7.</span><span class="sxs-lookup"><span data-stu-id="150f5-163">See Example 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="150f5-164">-IgnoreWhiteSpace</span><span class="sxs-lookup"><span data-stu-id="150f5-164">-IgnoreWhiteSpace</span></span>

<span data-ttu-id="150f5-165">Indica que o cmdlet ignora o espaço em branco em contagens de caracteres.</span><span class="sxs-lookup"><span data-stu-id="150f5-165">Indicates that the cmdlet ignores white space in character counts.</span></span>
<span data-ttu-id="150f5-166">Por padrão, o espaço em branco não é ignorado.</span><span class="sxs-lookup"><span data-stu-id="150f5-166">By default, white space is not ignored.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="150f5-167">-InputObject</span><span class="sxs-lookup"><span data-stu-id="150f5-167">-InputObject</span></span>

<span data-ttu-id="150f5-168">Especifica os objetos a serem medidos.</span><span class="sxs-lookup"><span data-stu-id="150f5-168">Specifies the objects to be measured.</span></span>
<span data-ttu-id="150f5-169">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="150f5-169">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="150f5-170">Quando você usa o parâmetro **InputObject** com `Measure-Object` , em vez de direcionar os resultados de comando para `Measure-Object` , o valor **InputObject** é tratado como um único objeto.</span><span class="sxs-lookup"><span data-stu-id="150f5-170">When you use the **InputObject** parameter with `Measure-Object`, instead of piping command results to `Measure-Object`, the **InputObject** value is treated as a single object.</span></span>

<span data-ttu-id="150f5-171">É recomendável que você use `Measure-Object` no pipeline se desejar medir uma coleção de objetos com base em se os objetos têm valores específicos nas propriedades definidas.</span><span class="sxs-lookup"><span data-stu-id="150f5-171">It is recommended that you use `Measure-Object` in the pipeline if you want to measure a collection of objects based on whether the objects have specific values in defined properties.</span></span>

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

### <span data-ttu-id="150f5-172">-Linha</span><span class="sxs-lookup"><span data-stu-id="150f5-172">-Line</span></span>

<span data-ttu-id="150f5-173">Indica que o cmdlet conta o número de linhas nos objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="150f5-173">Indicates that the cmdlet counts the number of lines in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="150f5-174">As opções de **palavra**, **Char** e **linha** contam *dentro* de cada objeto de entrada, bem como *entre* objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="150f5-174">The **Word**, **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="150f5-175">Consulte o exemplo 7.</span><span class="sxs-lookup"><span data-stu-id="150f5-175">See Example 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="150f5-176">-Máximo</span><span class="sxs-lookup"><span data-stu-id="150f5-176">-Maximum</span></span>

<span data-ttu-id="150f5-177">Indica que o cmdlet exibe o valor máximo das propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="150f5-177">Indicates that the cmdlet displays the maximum value of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="150f5-178">-Mínimo</span><span class="sxs-lookup"><span data-stu-id="150f5-178">-Minimum</span></span>

<span data-ttu-id="150f5-179">Indica que o cmdlet exibe o valor mínimo das propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="150f5-179">Indicates that the cmdlet displays the minimum value of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="150f5-180">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="150f5-180">-Property</span></span>

<span data-ttu-id="150f5-181">Especifica uma ou mais propriedades a serem medidas.</span><span class="sxs-lookup"><span data-stu-id="150f5-181">Specifies one or more properties to measure.</span></span> <span data-ttu-id="150f5-182">Se você não especificar nenhuma outra medida, `Measure-Object` o contará os objetos que têm as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="150f5-182">If you do not specify any other measures, `Measure-Object` counts the objects that have the properties you specify.</span></span>

<span data-ttu-id="150f5-183">O valor do parâmetro **Property** pode ser uma nova propriedade calculada.</span><span class="sxs-lookup"><span data-stu-id="150f5-183">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="150f5-184">A propriedade calculada deve ser um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="150f5-184">The calculated property must be a script block.</span></span> <span data-ttu-id="150f5-185">Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="150f5-185">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.PSPropertyExpression[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="150f5-186">-I</span><span class="sxs-lookup"><span data-stu-id="150f5-186">-StandardDeviation</span></span>

<span data-ttu-id="150f5-187">Indica que o cmdlet exibe o desvio padrão dos valores das propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="150f5-187">Indicates that the cmdlet displays the standard deviation of the values of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="150f5-188">-Sum</span><span class="sxs-lookup"><span data-stu-id="150f5-188">-Sum</span></span>

<span data-ttu-id="150f5-189">Indica que o cmdlet exibe a soma dos valores das propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="150f5-189">Indicates that the cmdlet displays the sum of the values of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="150f5-190">-Estatísticas</span><span class="sxs-lookup"><span data-stu-id="150f5-190">-AllStats</span></span>

<span data-ttu-id="150f5-191">Indica que o cmdlet exibe todas as estatísticas das propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="150f5-191">Indicates that the cmdlet displays all the statistics of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="150f5-192">-Palavra</span><span class="sxs-lookup"><span data-stu-id="150f5-192">-Word</span></span>

<span data-ttu-id="150f5-193">Indica que o cmdlet conta o número de palavras nos objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="150f5-193">Indicates that the cmdlet counts the number of words in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="150f5-194">As opções de **palavra**, **Char** e **linha** contam *dentro* de cada objeto de entrada, bem como *entre* objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="150f5-194">The **Word**, **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="150f5-195">Consulte o exemplo 7.</span><span class="sxs-lookup"><span data-stu-id="150f5-195">See Example 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="150f5-196">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="150f5-196">CommonParameters</span></span>

<span data-ttu-id="150f5-197">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="150f5-197">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="150f5-198">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="150f5-198">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="150f5-199">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="150f5-199">INPUTS</span></span>

### <span data-ttu-id="150f5-200">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="150f5-200">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="150f5-201">Você pode canalizar objetos para `Measure-Object` .</span><span class="sxs-lookup"><span data-stu-id="150f5-201">You can pipe objects to `Measure-Object`.</span></span>

## <span data-ttu-id="150f5-202">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="150f5-202">OUTPUTS</span></span>

### <span data-ttu-id="150f5-203">Microsoft. PowerShell. Commands. GenericMeasureInfo</span><span class="sxs-lookup"><span data-stu-id="150f5-203">Microsoft.PowerShell.Commands.GenericMeasureInfo</span></span>

### <span data-ttu-id="150f5-204">Microsoft. PowerShell. Commands. TextMeasureInfo</span><span class="sxs-lookup"><span data-stu-id="150f5-204">Microsoft.PowerShell.Commands.TextMeasureInfo</span></span>

<span data-ttu-id="150f5-205">Se você usar o parâmetro **Word** , `Measure-Object` retornará um objeto **TextMeasureInfo** .</span><span class="sxs-lookup"><span data-stu-id="150f5-205">If you use the **Word** parameter, `Measure-Object` returns a **TextMeasureInfo** object.</span></span>
<span data-ttu-id="150f5-206">Caso contrário, ele retorna um objeto **GenericMeasureInfo** .</span><span class="sxs-lookup"><span data-stu-id="150f5-206">Otherwise, it returns a **GenericMeasureInfo** object.</span></span>

## <span data-ttu-id="150f5-207">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="150f5-207">NOTES</span></span>

## <span data-ttu-id="150f5-208">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="150f5-208">RELATED LINKS</span></span>

[<span data-ttu-id="150f5-209">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="150f5-209">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="150f5-210">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="150f5-210">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="150f5-211">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="150f5-211">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="150f5-212">Group-Object</span><span class="sxs-lookup"><span data-stu-id="150f5-212">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="150f5-213">New-Object</span><span class="sxs-lookup"><span data-stu-id="150f5-213">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="150f5-214">Select-Object</span><span class="sxs-lookup"><span data-stu-id="150f5-214">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="150f5-215">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="150f5-215">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="150f5-216">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="150f5-216">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="150f5-217">Where-Object</span><span class="sxs-lookup"><span data-stu-id="150f5-217">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
