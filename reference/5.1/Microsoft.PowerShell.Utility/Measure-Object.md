---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/measure-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Measure-Object
ms.openlocfilehash: 5d4a27f1a1949056ca63b9b6a2340bf1226592e0
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "93195138"
---
# <span data-ttu-id="a04ca-103">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="a04ca-103">Measure-Object</span></span>

## <span data-ttu-id="a04ca-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="a04ca-104">SYNOPSIS</span></span>
<span data-ttu-id="a04ca-105">Calcula as propriedades numéricas de objetos e os caracteres, palavras e linhas em objetos de cadeia de caracteres, como arquivos de texto.</span><span class="sxs-lookup"><span data-stu-id="a04ca-105">Calculates the numeric properties of objects, and the characters, words, and lines in string objects, such as files of text.</span></span>

## <span data-ttu-id="a04ca-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a04ca-106">SYNTAX</span></span>

### <span data-ttu-id="a04ca-107">GenericMeasure (padrão)</span><span class="sxs-lookup"><span data-stu-id="a04ca-107">GenericMeasure (Default)</span></span>

```
Measure-Object [-InputObject <PSObject>] [[-Property] <String[]>] [-Sum] [-Average] [-Maximum] [-Minimum]
 [<CommonParameters>]
```

### <span data-ttu-id="a04ca-108">Textmeasure</span><span class="sxs-lookup"><span data-stu-id="a04ca-108">TextMeasure</span></span>

```
Measure-Object [-InputObject <PSObject>] [[-Property] <String[]>] [-Line] [-Word] [-Character]
 [-IgnoreWhiteSpace] [<CommonParameters>]
```

## <span data-ttu-id="a04ca-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a04ca-109">DESCRIPTION</span></span>

<span data-ttu-id="a04ca-110">O `Measure-Object` cmdlet calcula os valores de propriedade de determinados tipos de objeto.</span><span class="sxs-lookup"><span data-stu-id="a04ca-110">The `Measure-Object` cmdlet calculates the property values of certain types of object.</span></span>
<span data-ttu-id="a04ca-111">`Measure-Object` executa três tipos de medidas, dependendo dos parâmetros no comando.</span><span class="sxs-lookup"><span data-stu-id="a04ca-111">`Measure-Object` performs three types of measurements, depending on the parameters in the command.</span></span>

<span data-ttu-id="a04ca-112">O `Measure-Object` cmdlet executa cálculos nos valores de propriedade de objetos.</span><span class="sxs-lookup"><span data-stu-id="a04ca-112">The `Measure-Object` cmdlet performs calculations on the property values of objects.</span></span> <span data-ttu-id="a04ca-113">Você pode usar `Measure-Object` para contar objetos ou contar objetos com uma **Propriedade** especificada.</span><span class="sxs-lookup"><span data-stu-id="a04ca-113">You can use `Measure-Object` to count objects or count objects with a specified **Property** .</span></span> <span data-ttu-id="a04ca-114">Você também pode usar `Measure-Object` para calcular o **mínimo** , **máximo** , **soma** , **i** e **média** de valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="a04ca-114">You can also use `Measure-Object` to calculate the **Minimum** , **Maximum** , **Sum** , **StandardDeviation** and **Average** of numeric values.</span></span> <span data-ttu-id="a04ca-115">Para objetos de **cadeia de caracteres** , você também pode usar `Measure-Object` para contar o número de linhas, palavras e caracteres.</span><span class="sxs-lookup"><span data-stu-id="a04ca-115">For **String** objects, you can also use `Measure-Object` to count the number of lines, words, and characters.</span></span>

## <span data-ttu-id="a04ca-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="a04ca-116">EXAMPLES</span></span>

### <span data-ttu-id="a04ca-117">Exemplo 1: contar os arquivos e as pastas em um diretório</span><span class="sxs-lookup"><span data-stu-id="a04ca-117">Example 1: Count the files and folders in a directory</span></span>

<span data-ttu-id="a04ca-118">Esse comando conta os arquivos e pastas no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="a04ca-118">This command counts the files and folders in the current directory.</span></span>

```powershell
Get-ChildItem | Measure-Object
```

### <span data-ttu-id="a04ca-119">Exemplo 2: medir os arquivos em um diretório</span><span class="sxs-lookup"><span data-stu-id="a04ca-119">Example 2: Measure the files in a directory</span></span>

<span data-ttu-id="a04ca-120">Esse comando exibe o **mínimo** , o **máximo** e a **soma** dos tamanhos de todos os arquivos no diretório atual e o tamanho médio de um arquivo no diretório.</span><span class="sxs-lookup"><span data-stu-id="a04ca-120">This command displays the **Minimum** , **Maximum** , and **Sum** of the sizes of all files in the current directory, and the average size of a file in the directory.</span></span>

```powershell
Get-ChildItem | Measure-Object -Property length -Minimum -Maximum -Average
```

### <span data-ttu-id="a04ca-121">Exemplo 3: medir o texto em um arquivo de texto</span><span class="sxs-lookup"><span data-stu-id="a04ca-121">Example 3: Measure text in a text file</span></span>

<span data-ttu-id="a04ca-122">Este comando exibe o número de caracteres, palavras e linhas no arquivo Text.txt.</span><span class="sxs-lookup"><span data-stu-id="a04ca-122">This command displays the number of characters, words, and lines in the Text.txt file.</span></span>
<span data-ttu-id="a04ca-123">Sem o parâmetro **RAW** , `Get-Content` o gera o arquivo como uma matriz de linhas.</span><span class="sxs-lookup"><span data-stu-id="a04ca-123">Without the **Raw** parameter, `Get-Content` outputs the file as an array of lines.</span></span>

<span data-ttu-id="a04ca-124">O primeiro comando usa `Set-Content` para adicionar um texto padrão a um arquivo.</span><span class="sxs-lookup"><span data-stu-id="a04ca-124">The first command uses `Set-Content` to add some default text to a file.</span></span>

```powershell
"One", "Two", "Three", "Four" | Set-Content -Path C:\Temp\tmp.txt
Get-Content C:\Temp\tmp.txt | Measure-Object -Character -Line -Word
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    4     4         15
```

### <span data-ttu-id="a04ca-125">Exemplo 4: objetos de medida que contêm uma propriedade especificada</span><span class="sxs-lookup"><span data-stu-id="a04ca-125">Example 4: Measure objects containing a specified Property</span></span>

<span data-ttu-id="a04ca-126">Este exemplo conta o número de objetos que têm uma propriedade **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="a04ca-126">This example counts the number of objects that have a **DisplayName** property.</span></span> <span data-ttu-id="a04ca-127">Os dois primeiros comandos recuperam todos os serviços e processos no computador local.</span><span class="sxs-lookup"><span data-stu-id="a04ca-127">The first two commands retrieve all the services and processes on the local machine.</span></span> <span data-ttu-id="a04ca-128">O terceiro comando conta o número combinado de serviços e processos.</span><span class="sxs-lookup"><span data-stu-id="a04ca-128">The third command counts the combined number of services and processes.</span></span> <span data-ttu-id="a04ca-129">O último comando combina as duas coleções e canaliza o resultado para `Measure-Object` .</span><span class="sxs-lookup"><span data-stu-id="a04ca-129">The last command combines the two collections and pipes the result to `Measure-Object`.</span></span>

<span data-ttu-id="a04ca-130">O objeto **System. Diagnostics. Process** não tem uma propriedade **DisplayName** e é deixado da contagem final.</span><span class="sxs-lookup"><span data-stu-id="a04ca-130">The **System.Diagnostics.Process** object does not have a **DisplayName** property, and is left out of the final count.</span></span>

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

### <span data-ttu-id="a04ca-131">Exemplo 5: medir o conteúdo de um arquivo CSV</span><span class="sxs-lookup"><span data-stu-id="a04ca-131">Example 5: Measure the contents of a CSV file</span></span>

<span data-ttu-id="a04ca-132">Este comando calcula os médio anos de serviço dos funcionários de uma empresa.</span><span class="sxs-lookup"><span data-stu-id="a04ca-132">This command calculates the average years of service of the employees of a company.</span></span>

<span data-ttu-id="a04ca-133">O `ServiceYrs.csv` arquivo é um arquivo CSV que contém o número do funcionário e os anos de serviço de cada funcionário.</span><span class="sxs-lookup"><span data-stu-id="a04ca-133">The `ServiceYrs.csv` file is a CSV file that contains the employee number and years of service of each employee.</span></span> <span data-ttu-id="a04ca-134">A primeira linha da tabela é uma linha de cabeçalho de **empno** , **anos** .</span><span class="sxs-lookup"><span data-stu-id="a04ca-134">The first row in the table is a header row of **EmpNo** , **Years** .</span></span>

<span data-ttu-id="a04ca-135">Quando você usa `Import-Csv` o para importar o arquivo, o resultado é um **PSCustomObject** com as propriedades de observação de **empno** e **anos** .</span><span class="sxs-lookup"><span data-stu-id="a04ca-135">When you use `Import-Csv` to import the file, the result is a **PSCustomObject** with note properties of **EmpNo** and **Years** .</span></span>
<span data-ttu-id="a04ca-136">Você pode usar `Measure-Object` para calcular os valores dessas propriedades, assim como qualquer outra propriedade de um objeto.</span><span class="sxs-lookup"><span data-stu-id="a04ca-136">You can use `Measure-Object` to calculate the values of these properties, just like any other property of an object.</span></span>

```powershell
Import-Csv d:\test\serviceyrs.csv | Measure-Object -Property years -Minimum -Maximum -Average
```

### <span data-ttu-id="a04ca-137">Exemplo 6: medir valores Boolianos</span><span class="sxs-lookup"><span data-stu-id="a04ca-137">Example 6: Measure Boolean values</span></span>

<span data-ttu-id="a04ca-138">Este exemplo demonstra como o `Measure-Object` pode medir valores Boolianos.</span><span class="sxs-lookup"><span data-stu-id="a04ca-138">This example demonstrates how the `Measure-Object` can measure Boolean values.</span></span>
<span data-ttu-id="a04ca-139">Nesse caso, ele usa a propriedade **PSIsContainer** **booliana** PsIsContainer para medir a incidência de pastas (vs. Files) no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="a04ca-139">In this case, it uses the **PSIsContainer** **Boolean** property to measure the incidence of folders (vs. files) in the current directory.</span></span>

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

### <span data-ttu-id="a04ca-140">Exemplo 7: cadeias de caracteres de medida</span><span class="sxs-lookup"><span data-stu-id="a04ca-140">Example 7: Measure strings</span></span>

<span data-ttu-id="a04ca-141">O exemplo a seguir mede o número de linhas, primeiro uma única cadeia de caracteres e, em seguida, em várias cadeias.</span><span class="sxs-lookup"><span data-stu-id="a04ca-141">The following example measures the number of lines, first a single string, then across several strings.</span></span> <span data-ttu-id="a04ca-142">O caractere de nova linha <code>\`n</code> separa cadeias de caracteres em várias linhas.</span><span class="sxs-lookup"><span data-stu-id="a04ca-142">The newline character <code>\`n</code> separates strings into multiple lines.</span></span>

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

## <span data-ttu-id="a04ca-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a04ca-143">PARAMETERS</span></span>

### <span data-ttu-id="a04ca-144">-Média</span><span class="sxs-lookup"><span data-stu-id="a04ca-144">-Average</span></span>

<span data-ttu-id="a04ca-145">Indica que o cmdlet exibe o valor médio das propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="a04ca-145">Indicates that the cmdlet displays the average value of the specified properties.</span></span>

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

### <span data-ttu-id="a04ca-146">-Caractere</span><span class="sxs-lookup"><span data-stu-id="a04ca-146">-Character</span></span>

<span data-ttu-id="a04ca-147">Indica que o cmdlet conta o número de caracteres nos objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="a04ca-147">Indicates that the cmdlet counts the number of characters in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="a04ca-148">As opções de **palavra** , **Char** e **linha** contam *dentro* de cada objeto de entrada, bem como *entre* objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="a04ca-148">The **Word** , **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="a04ca-149">Consulte o exemplo 7.</span><span class="sxs-lookup"><span data-stu-id="a04ca-149">See Example 7.</span></span>

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

### <span data-ttu-id="a04ca-150">-IgnoreWhiteSpace</span><span class="sxs-lookup"><span data-stu-id="a04ca-150">-IgnoreWhiteSpace</span></span>

<span data-ttu-id="a04ca-151">Indica que o cmdlet ignora o espaço em branco em contagens de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a04ca-151">Indicates that the cmdlet ignores white space in character counts.</span></span>
<span data-ttu-id="a04ca-152">Por padrão, o espaço em branco não é ignorado.</span><span class="sxs-lookup"><span data-stu-id="a04ca-152">By default, white space is not ignored.</span></span>

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

### <span data-ttu-id="a04ca-153">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a04ca-153">-InputObject</span></span>

<span data-ttu-id="a04ca-154">Especifica os objetos a serem medidos.</span><span class="sxs-lookup"><span data-stu-id="a04ca-154">Specifies the objects to be measured.</span></span>
<span data-ttu-id="a04ca-155">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="a04ca-155">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="a04ca-156">Quando você usa o parâmetro **InputObject** com `Measure-Object` , em vez de direcionar os resultados de comando para `Measure-Object` , o valor **InputObject** é tratado como um único objeto.</span><span class="sxs-lookup"><span data-stu-id="a04ca-156">When you use the **InputObject** parameter with `Measure-Object`, instead of piping command results to `Measure-Object`, the **InputObject** value is treated as a single object.</span></span>

<span data-ttu-id="a04ca-157">É recomendável que você use `Measure-Object` no pipeline se desejar medir uma coleção de objetos com base em se os objetos têm valores específicos nas propriedades definidas.</span><span class="sxs-lookup"><span data-stu-id="a04ca-157">It is recommended that you use `Measure-Object` in the pipeline if you want to measure a collection of objects based on whether the objects have specific values in defined properties.</span></span>

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

### <span data-ttu-id="a04ca-158">-Linha</span><span class="sxs-lookup"><span data-stu-id="a04ca-158">-Line</span></span>

<span data-ttu-id="a04ca-159">Indica que o cmdlet conta o número de linhas nos objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="a04ca-159">Indicates that the cmdlet counts the number of lines in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="a04ca-160">As opções de **palavra** , **Char** e **linha** contam *dentro* de cada objeto de entrada, bem como *entre* objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="a04ca-160">The **Word** , **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="a04ca-161">Consulte o exemplo 7.</span><span class="sxs-lookup"><span data-stu-id="a04ca-161">See Example 7.</span></span>

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

### <span data-ttu-id="a04ca-162">-Máximo</span><span class="sxs-lookup"><span data-stu-id="a04ca-162">-Maximum</span></span>

<span data-ttu-id="a04ca-163">Indica que o cmdlet exibe o valor máximo das propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="a04ca-163">Indicates that the cmdlet displays the maximum value of the specified properties.</span></span>

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

### <span data-ttu-id="a04ca-164">-Mínimo</span><span class="sxs-lookup"><span data-stu-id="a04ca-164">-Minimum</span></span>

<span data-ttu-id="a04ca-165">Indica que o cmdlet exibe o valor mínimo das propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="a04ca-165">Indicates that the cmdlet displays the minimum value of the specified properties.</span></span>

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

### <span data-ttu-id="a04ca-166">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="a04ca-166">-Property</span></span>

<span data-ttu-id="a04ca-167">Especifica uma ou mais propriedades a serem medidas.</span><span class="sxs-lookup"><span data-stu-id="a04ca-167">Specifies one or more properties to measure.</span></span> <span data-ttu-id="a04ca-168">Se você não especificar nenhuma outra medida, `Measure-Object` o contará os objetos que têm as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="a04ca-168">If you do not specify any other measures, `Measure-Object` counts the objects that have the properties you specify.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="a04ca-169">-Sum</span><span class="sxs-lookup"><span data-stu-id="a04ca-169">-Sum</span></span>

<span data-ttu-id="a04ca-170">Indica que o cmdlet exibe a soma dos valores das propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="a04ca-170">Indicates that the cmdlet displays the sum of the values of the specified properties.</span></span>

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

### <span data-ttu-id="a04ca-171">-Palavra</span><span class="sxs-lookup"><span data-stu-id="a04ca-171">-Word</span></span>

<span data-ttu-id="a04ca-172">Indica que o cmdlet conta o número de palavras nos objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="a04ca-172">Indicates that the cmdlet counts the number of words in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="a04ca-173">As opções de **palavra** , **Char** e **linha** contam *dentro* de cada objeto de entrada, bem como *entre* objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="a04ca-173">The **Word** , **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="a04ca-174">Consulte o exemplo 7.</span><span class="sxs-lookup"><span data-stu-id="a04ca-174">See Example 7.</span></span>

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

### <span data-ttu-id="a04ca-175">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a04ca-175">CommonParameters</span></span>

<span data-ttu-id="a04ca-176">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a04ca-176">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a04ca-177">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a04ca-177">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a04ca-178">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="a04ca-178">INPUTS</span></span>

### <span data-ttu-id="a04ca-179">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="a04ca-179">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="a04ca-180">Você pode canalizar objetos para `Measure-Object` .</span><span class="sxs-lookup"><span data-stu-id="a04ca-180">You can pipe objects to `Measure-Object`.</span></span>

## <span data-ttu-id="a04ca-181">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="a04ca-181">OUTPUTS</span></span>

### <span data-ttu-id="a04ca-182">Microsoft. PowerShell. Commands. GenericMeasureInfo</span><span class="sxs-lookup"><span data-stu-id="a04ca-182">Microsoft.PowerShell.Commands.GenericMeasureInfo</span></span>

### <span data-ttu-id="a04ca-183">Microsoft. PowerShell. Commands. TextMeasureInfo</span><span class="sxs-lookup"><span data-stu-id="a04ca-183">Microsoft.PowerShell.Commands.TextMeasureInfo</span></span>

<span data-ttu-id="a04ca-184">Se você usar o parâmetro **Word** , `Measure-Object` retornará um objeto **TextMeasureInfo** .</span><span class="sxs-lookup"><span data-stu-id="a04ca-184">If you use the **Word** parameter, `Measure-Object` returns a **TextMeasureInfo** object.</span></span>
<span data-ttu-id="a04ca-185">Caso contrário, ele retorna um objeto **GenericMeasureInfo** .</span><span class="sxs-lookup"><span data-stu-id="a04ca-185">Otherwise, it returns a **GenericMeasureInfo** object.</span></span>

## <span data-ttu-id="a04ca-186">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="a04ca-186">NOTES</span></span>

## <span data-ttu-id="a04ca-187">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="a04ca-187">RELATED LINKS</span></span>

[<span data-ttu-id="a04ca-188">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="a04ca-188">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="a04ca-189">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="a04ca-189">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="a04ca-190">Group-Object</span><span class="sxs-lookup"><span data-stu-id="a04ca-190">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="a04ca-191">New-Object</span><span class="sxs-lookup"><span data-stu-id="a04ca-191">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="a04ca-192">Select-Object</span><span class="sxs-lookup"><span data-stu-id="a04ca-192">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="a04ca-193">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="a04ca-193">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="a04ca-194">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="a04ca-194">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="a04ca-195">Where-Object</span><span class="sxs-lookup"><span data-stu-id="a04ca-195">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
