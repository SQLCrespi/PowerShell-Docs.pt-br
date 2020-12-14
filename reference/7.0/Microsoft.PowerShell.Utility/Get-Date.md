---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Date
ms.openlocfilehash: 4ae3734d0ce41ef2faa7bcf3e07f136b9e9916a2
ms.sourcegitcommit: 077488408c820c860131382324bdd576d0edf52a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95514952"
---
# <span data-ttu-id="d5625-103">Get-Date</span><span class="sxs-lookup"><span data-stu-id="d5625-103">Get-Date</span></span>

## <span data-ttu-id="d5625-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d5625-104">SYNOPSIS</span></span>
<span data-ttu-id="d5625-105">Obtém a data e hora atuais.</span><span class="sxs-lookup"><span data-stu-id="d5625-105">Gets the current date and time.</span></span>

## <span data-ttu-id="d5625-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d5625-106">SYNTAX</span></span>

### <span data-ttu-id="d5625-107">NET (padrão)</span><span class="sxs-lookup"><span data-stu-id="d5625-107">net (Default)</span></span>

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-Format <String>] [<CommonParameters>]
```

### <span data-ttu-id="d5625-108">UFormat</span><span class="sxs-lookup"><span data-stu-id="d5625-108">UFormat</span></span>

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-UFormat <String>] [<CommonParameters>]
```

## <span data-ttu-id="d5625-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d5625-109">DESCRIPTION</span></span>

<span data-ttu-id="d5625-110">O `Get-Date` cmdlet obtém um objeto **DateTime** que representa a data atual ou uma data que você especifica.</span><span class="sxs-lookup"><span data-stu-id="d5625-110">The `Get-Date` cmdlet gets a **DateTime** object that represents the current date or a date that you specify.</span></span> <span data-ttu-id="d5625-111">`Get-Date` pode formatar a data e a hora em vários formatos .NET e UNIX.</span><span class="sxs-lookup"><span data-stu-id="d5625-111">`Get-Date` can format the date and time in several .NET and UNIX formats.</span></span> <span data-ttu-id="d5625-112">Você pode usar `Get-Date` para gerar uma cadeia de caracteres de caractere de data ou hora e, em seguida, enviar a cadeia de caracteres para outros cmdlets ou programas.</span><span class="sxs-lookup"><span data-stu-id="d5625-112">You can use `Get-Date` to generate a date or time character string, and then send the string to other cmdlets or programs.</span></span>

<span data-ttu-id="d5625-113">`Get-Date` usa as configurações de cultura do computador para determinar como a saída é formatada.</span><span class="sxs-lookup"><span data-stu-id="d5625-113">`Get-Date` uses the computer's culture settings to determine how the output is formatted.</span></span> <span data-ttu-id="d5625-114">Para exibir as configurações do computador, use `(Get-Culture).DateTimeFormat` .</span><span class="sxs-lookup"><span data-stu-id="d5625-114">To view your computer's settings, use `(Get-Culture).DateTimeFormat`.</span></span>

## <span data-ttu-id="d5625-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d5625-115">EXAMPLES</span></span>

### <span data-ttu-id="d5625-116">Exemplo 1: obter a data e a hora atuais</span><span class="sxs-lookup"><span data-stu-id="d5625-116">Example 1: Get the current date and time</span></span>

<span data-ttu-id="d5625-117">Neste exemplo, `Get-Date` exibe a data e hora atuais do sistema.</span><span class="sxs-lookup"><span data-stu-id="d5625-117">In this example, `Get-Date` displays the current system date and time.</span></span> <span data-ttu-id="d5625-118">A saída está nos formatos de longa data e de hora longa.</span><span class="sxs-lookup"><span data-stu-id="d5625-118">The output is in the long-date and long-time formats.</span></span>

```powershell
Get-Date
```

```Output
Tuesday, June 25, 2019 14:53:32
```

### <span data-ttu-id="d5625-119">Exemplo 2: obter elementos da data e hora atuais</span><span class="sxs-lookup"><span data-stu-id="d5625-119">Example 2: Get elements of the current date and time</span></span>

<span data-ttu-id="d5625-120">Este exemplo mostra como usar `Get-Date` para obter o elemento Date ou time.</span><span class="sxs-lookup"><span data-stu-id="d5625-120">This example shows how to use `Get-Date` to get either the date or time element.</span></span> <span data-ttu-id="d5625-121">O parâmetro usa os argumentos **Date**, **time** ou **DateTime**.</span><span class="sxs-lookup"><span data-stu-id="d5625-121">The parameter uses the arguments **Date**, **Time**, or **DateTime**.</span></span>

```powershell
Get-Date -DisplayHint Date
```

```Output
Tuesday, June 25, 2019
```

<span data-ttu-id="d5625-122">`Get-Date` usa o parâmetro **DisplayHint** com o argumento **Date** para obter apenas a data.</span><span class="sxs-lookup"><span data-stu-id="d5625-122">`Get-Date` uses the **DisplayHint** parameter with the **Date** argument to get only the date.</span></span>

### <span data-ttu-id="d5625-123">Exemplo 3: obter a data e a hora com um especificador de formato .NET</span><span class="sxs-lookup"><span data-stu-id="d5625-123">Example 3: Get the date and time with a .NET format specifier</span></span>

<span data-ttu-id="d5625-124">Neste exemplo, um especificador de formato .NET é usado para personalizar o formato da saída.</span><span class="sxs-lookup"><span data-stu-id="d5625-124">In this example, a .NET format specifier is used to customize the output's format.</span></span> <span data-ttu-id="d5625-125">A saída é um objeto de **cadeia de caracteres** .</span><span class="sxs-lookup"><span data-stu-id="d5625-125">The output is a **String** object.</span></span>

```powershell
Get-Date -Format "dddd MM/dd/yyyy HH:mm K"
```

```Output
Tuesday 06/25/2019 16:17 -07:00
```

<span data-ttu-id="d5625-126">`Get-Date` usa o parâmetro **Format** para especificar vários especificadores de formato.</span><span class="sxs-lookup"><span data-stu-id="d5625-126">`Get-Date` uses the **Format** parameter to specify several format specifiers.</span></span>

<span data-ttu-id="d5625-127">Os especificadores de formato .NET usados neste exemplo são definidos da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="d5625-127">The .NET format specifiers used in this example are defined as follows:</span></span>

| <span data-ttu-id="d5625-128">Especificador</span><span class="sxs-lookup"><span data-stu-id="d5625-128">Specifier</span></span> | <span data-ttu-id="d5625-129">Definição</span><span class="sxs-lookup"><span data-stu-id="d5625-129">Definition</span></span> |
| --- | --- |
| `dddd` | <span data-ttu-id="d5625-130">Dia da semana-nome completo</span><span class="sxs-lookup"><span data-stu-id="d5625-130">Day of the week - full name</span></span> |
| `MM` | <span data-ttu-id="d5625-131">Número do mês</span><span class="sxs-lookup"><span data-stu-id="d5625-131">Month number</span></span> |
| `dd` | <span data-ttu-id="d5625-132">Dia do mês-2 dígitos</span><span class="sxs-lookup"><span data-stu-id="d5625-132">Day of the month - 2 digits</span></span> |
| `yyyy` | <span data-ttu-id="d5625-133">Ano no formato de 4 dígitos</span><span class="sxs-lookup"><span data-stu-id="d5625-133">Year in 4-digit format</span></span> |
| `HH:mm` | <span data-ttu-id="d5625-134">Tempo no formato de 24 horas-sem segundos</span><span class="sxs-lookup"><span data-stu-id="d5625-134">Time in 24-hour format -no seconds</span></span> |
| `K` | <span data-ttu-id="d5625-135">Deslocamento de fuso horário da coordenada de tempo universal (UTC)</span><span class="sxs-lookup"><span data-stu-id="d5625-135">Time zone offset from Universal Time Coordinate (UTC)</span></span> |

<span data-ttu-id="d5625-136">Para obter mais informações sobre especificadores de formato .NET, consulte [cadeias de caracteres de formato personalizado de data e hora](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span><span class="sxs-lookup"><span data-stu-id="d5625-136">For more information about .NET format specifiers, see [Custom date and time format strings](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span></span>

### <span data-ttu-id="d5625-137">Exemplo 4: obter a data e a hora com um especificador UFormat</span><span class="sxs-lookup"><span data-stu-id="d5625-137">Example 4: Get the date and time with a UFormat specifier</span></span>

<span data-ttu-id="d5625-138">Neste exemplo, vários especificadores de formato **uFormat** são usados para personalizar o formato da saída.</span><span class="sxs-lookup"><span data-stu-id="d5625-138">In this example, several **UFormat** format specifiers are used to customize the output's format.</span></span>
<span data-ttu-id="d5625-139">A saída é um objeto de **cadeia de caracteres** .</span><span class="sxs-lookup"><span data-stu-id="d5625-139">The output is a **String** object.</span></span>

```powershell
Get-Date -UFormat "%A %m/%d/%Y %R %Z"
```

```Output
Tuesday 06/25/2019 16:19 -07
```

<span data-ttu-id="d5625-140">`Get-Date` usa o parâmetro **uFormat** para especificar vários especificadores de formato.</span><span class="sxs-lookup"><span data-stu-id="d5625-140">`Get-Date` uses the **UFormat** parameter to specify several format specifiers.</span></span>

<span data-ttu-id="d5625-141">Os especificadores de formato **uFormat** usados neste exemplo são definidos da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="d5625-141">The **UFormat** format specifiers used in this example are defined as follows:</span></span>

| <span data-ttu-id="d5625-142">Especificador</span><span class="sxs-lookup"><span data-stu-id="d5625-142">Specifier</span></span> | <span data-ttu-id="d5625-143">Definição</span><span class="sxs-lookup"><span data-stu-id="d5625-143">Definition</span></span> |
| --- | --- |
| `%A` | <span data-ttu-id="d5625-144">Dia da semana-nome completo</span><span class="sxs-lookup"><span data-stu-id="d5625-144">Day of the week - full name</span></span> |
| `%m` | <span data-ttu-id="d5625-145">Número do mês</span><span class="sxs-lookup"><span data-stu-id="d5625-145">Month number</span></span> |
| `%d` | <span data-ttu-id="d5625-146">Dia do mês-2 dígitos</span><span class="sxs-lookup"><span data-stu-id="d5625-146">Day of the month - 2 digits</span></span> |
| `%Y` | <span data-ttu-id="d5625-147">Ano no formato de 4 dígitos</span><span class="sxs-lookup"><span data-stu-id="d5625-147">Year in 4-digit format</span></span> |
| `%R` | <span data-ttu-id="d5625-148">Tempo no formato de 24 horas-sem segundos</span><span class="sxs-lookup"><span data-stu-id="d5625-148">Time in 24-hour format -no seconds</span></span> |
| `%Z` | <span data-ttu-id="d5625-149">Deslocamento de fuso horário da coordenada de tempo universal (UTC)</span><span class="sxs-lookup"><span data-stu-id="d5625-149">Time zone offset from Universal Time Coordinate (UTC)</span></span> |

<span data-ttu-id="d5625-150">Para obter uma lista de especificadores de formato **uFormat** válidos, consulte a seção [observações](#notes) .</span><span class="sxs-lookup"><span data-stu-id="d5625-150">For a list of valid **UFormat** format specifiers, see the [Notes](#notes) section.</span></span>

### <span data-ttu-id="d5625-151">Exemplo 5: obter o dia do ano de uma data</span><span class="sxs-lookup"><span data-stu-id="d5625-151">Example 5: Get a date's day of the year</span></span>

<span data-ttu-id="d5625-152">Neste exemplo, uma propriedade é usada para obter o dia numérico do ano.</span><span class="sxs-lookup"><span data-stu-id="d5625-152">In this example, a property is used to get the numeric day of the year.</span></span>

<span data-ttu-id="d5625-153">O calendário gregoriano tem 365 dias, exceto os anos bissextos que têm 366 dias.</span><span class="sxs-lookup"><span data-stu-id="d5625-153">The Gregorian calendar has 365 days, except for leap years that have 366 days.</span></span> <span data-ttu-id="d5625-154">Por exemplo, 31 de dezembro de 2020 é o dia 366.</span><span class="sxs-lookup"><span data-stu-id="d5625-154">For example, December 31, 2020 is day 366.</span></span>

```powershell
(Get-Date -Year 2020 -Month 12 -Day 31).DayOfYear
```

```Output
366
```

<span data-ttu-id="d5625-155">`Get-Date` usa três parâmetros para especificar a data: **ano**, **mês** e **dia**.</span><span class="sxs-lookup"><span data-stu-id="d5625-155">`Get-Date` uses three parameters to specify the date: **Year**, **Month**, and **Day**.</span></span> <span data-ttu-id="d5625-156">O comando é encapsulado com parênteses para que o resultado seja avaliado pela propriedade **DayofYear** .</span><span class="sxs-lookup"><span data-stu-id="d5625-156">The command is wrapped with parentheses so that the result is evaluated by the **DayofYear** property.</span></span>

### <span data-ttu-id="d5625-157">Exemplo 6: verificar se uma data está ajustada para o horário de verão</span><span class="sxs-lookup"><span data-stu-id="d5625-157">Example 6: Check if a date is adjusted for daylight savings time</span></span>

<span data-ttu-id="d5625-158">Este exemplo usa um método booliano para verificar se uma data é ajustada pelo horário de verão.</span><span class="sxs-lookup"><span data-stu-id="d5625-158">This example uses a boolean method to verify if a date is adjusted by daylight savings time.</span></span>

```powershell
$DST = Get-Date
$DST.IsDaylightSavingTime()
```

```Output
True
```

<span data-ttu-id="d5625-159">Uma variável, `$DST` armazena o resultado de `Get-Date` .</span><span class="sxs-lookup"><span data-stu-id="d5625-159">A variable, `$DST` stores the result of `Get-Date`.</span></span> <span data-ttu-id="d5625-160">`$DST` usa o método **IsDaylightSavingTime** para testar se a data é ajustada para o horário de verão.</span><span class="sxs-lookup"><span data-stu-id="d5625-160">`$DST` uses the **IsDaylightSavingTime** method to test if the date is adjusted for daylight savings time.</span></span>

### <span data-ttu-id="d5625-161">Exemplo 7: converter a hora atual em hora UTC</span><span class="sxs-lookup"><span data-stu-id="d5625-161">Example 7: Convert the current time to UTC time</span></span>

<span data-ttu-id="d5625-162">Neste exemplo, a hora atual é convertida em hora UTC.</span><span class="sxs-lookup"><span data-stu-id="d5625-162">In this example, the current time is converted to UTC time.</span></span> <span data-ttu-id="d5625-163">O deslocamento UTC para a localidade do sistema é usado para converter a hora.</span><span class="sxs-lookup"><span data-stu-id="d5625-163">The UTC offset for the system's locale is used to convert the time.</span></span> <span data-ttu-id="d5625-164">Uma tabela na seção [observações](#notes) lista os especificadores de formato **uFormat** válidos.</span><span class="sxs-lookup"><span data-stu-id="d5625-164">A table in the [Notes](#notes) section lists the valid **UFormat** format specifiers.</span></span>

```powershell
Get-Date -UFormat "%A %B/%d/%Y %T %Z"
$Time = Get-Date
$Time.ToUniversalTime()
```

```Output
Wednesday June/26/2019 10:45:26 -07

Wednesday, June 26, 2019 17:45:26
```

<span data-ttu-id="d5625-165">`Get-Date` usa o parâmetro **uFormat** com especificadores de formato para exibir a data e a hora atuais do sistema.</span><span class="sxs-lookup"><span data-stu-id="d5625-165">`Get-Date` uses the **UFormat** parameter with format specifiers to display the current system date and time.</span></span> <span data-ttu-id="d5625-166">O especificador de formato **% Z** representa o deslocamento UTC de **-07**.</span><span class="sxs-lookup"><span data-stu-id="d5625-166">The format specifier **%Z** represents the UTC offset of **-07**.</span></span>

<span data-ttu-id="d5625-167">A `$Time` variável armazena a data e a hora atuais do sistema.</span><span class="sxs-lookup"><span data-stu-id="d5625-167">The `$Time` variable stores the current system date and time.</span></span> <span data-ttu-id="d5625-168">`$Time` usa o método **ToUniversalTime ()** para converter a hora com base no deslocamento UTC do computador.</span><span class="sxs-lookup"><span data-stu-id="d5625-168">`$Time` uses the **ToUniversalTime()** method to convert the time based on the computer's UTC offset.</span></span>

### <span data-ttu-id="d5625-169">Exemplo 8: criar um carimbo de data/hora</span><span class="sxs-lookup"><span data-stu-id="d5625-169">Example 8: Create a timestamp</span></span>

<span data-ttu-id="d5625-170">Neste exemplo, um especificador de formato cria um objeto de **cadeia de caracteres** de carimbo de data/hora para um nome de diretório.</span><span class="sxs-lookup"><span data-stu-id="d5625-170">In this example, a format specifier creates a timestamp **String** object for a directory name.</span></span> <span data-ttu-id="d5625-171">O timestamp inclui a data, a hora e o deslocamento UTC.</span><span class="sxs-lookup"><span data-stu-id="d5625-171">The timestamp includes the date, time, and UTC offset.</span></span>

```powershell
$timestamp = Get-Date -Format o | ForEach-Object { $_ -replace ":", "." }
New-Item -Path C:\Test\$timestamp -Type Directory
```

```Output
    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         6/27/2019    07:59                2019-06-27T07.59.24.4603750-07.00
```

<span data-ttu-id="d5625-172">A `$timestamp` variável armazena os resultados de um `Get-Date` comando.</span><span class="sxs-lookup"><span data-stu-id="d5625-172">The `$timestamp` variable stores the results of a `Get-Date` command.</span></span> <span data-ttu-id="d5625-173">`Get-Date` usa o parâmetro **Format** com o especificador de formato de minúsculas `o` para criar um objeto de **cadeia de caracteres** de carimbo de data/hora.</span><span class="sxs-lookup"><span data-stu-id="d5625-173">`Get-Date` uses the **Format** parameter with the format specifier of lowercase `o` to create a timestamp **String** object.</span></span> <span data-ttu-id="d5625-174">O objeto é enviado ao pipeline para `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="d5625-174">The object is sent down the pipeline to `ForEach-Object`.</span></span> <span data-ttu-id="d5625-175">Um **scriptblock** contém a `$_` variável que representa o objeto de pipeline atual.</span><span class="sxs-lookup"><span data-stu-id="d5625-175">A **ScriptBlock** contains the `$_` variable that represents the current pipeline object.</span></span> <span data-ttu-id="d5625-176">A cadeia de caracteres de carimbo de data/hora é delimitada por dois-pontos que são substituídos por pontos.</span><span class="sxs-lookup"><span data-stu-id="d5625-176">The timestamp string is delimited by colons that are replaced by periods.</span></span>

<span data-ttu-id="d5625-177">`New-Item` usa o parâmetro **path** para especificar o local de um novo diretório.</span><span class="sxs-lookup"><span data-stu-id="d5625-177">`New-Item` uses the **Path** parameter to specify the location for a new directory.</span></span> <span data-ttu-id="d5625-178">O caminho inclui a `$timestamp` variável como o nome do diretório.</span><span class="sxs-lookup"><span data-stu-id="d5625-178">The path includes the `$timestamp` variable as the directory name.</span></span> <span data-ttu-id="d5625-179">O parâmetro de **tipo** especifica que um diretório é criado.</span><span class="sxs-lookup"><span data-stu-id="d5625-179">The **Type** parameter specifies that a directory is created.</span></span>

## <span data-ttu-id="d5625-180">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d5625-180">PARAMETERS</span></span>

### <span data-ttu-id="d5625-181">-Data</span><span class="sxs-lookup"><span data-stu-id="d5625-181">-Date</span></span>

<span data-ttu-id="d5625-182">Especifica uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="d5625-182">Specifies a date and time.</span></span> <span data-ttu-id="d5625-183">O tempo é opcional e, se não for especificado, retornará 00:00:00.</span><span class="sxs-lookup"><span data-stu-id="d5625-183">Time is optional and if not specified, returns 00:00:00.</span></span>

<span data-ttu-id="d5625-184">Insira a data e a hora em um formato padrão para a localidade do sistema.</span><span class="sxs-lookup"><span data-stu-id="d5625-184">Enter the date and time in a format that is standard for the system locale.</span></span>

<span data-ttu-id="d5625-185">Por exemplo, em inglês americano:</span><span class="sxs-lookup"><span data-stu-id="d5625-185">For example, in US English:</span></span>

<span data-ttu-id="d5625-186">`Get-Date -Date "6/25/2019 12:30:22"` Retorna terça-feira, 25 de junho de 2019 12:30:22</span><span class="sxs-lookup"><span data-stu-id="d5625-186">`Get-Date -Date "6/25/2019 12:30:22"` returns Tuesday, June 25, 2019 12:30:22</span></span>

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases: LastWriteTime

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d5625-187">-Dia</span><span class="sxs-lookup"><span data-stu-id="d5625-187">-Day</span></span>

<span data-ttu-id="d5625-188">Especifica o dia do mês que é exibido.</span><span class="sxs-lookup"><span data-stu-id="d5625-188">Specifies the day of the month that is displayed.</span></span> <span data-ttu-id="d5625-189">Insira um valor de 1 a 31.</span><span class="sxs-lookup"><span data-stu-id="d5625-189">Enter a value from 1 to 31.</span></span>

<span data-ttu-id="d5625-190">Se o valor especificado for maior que o número de dias em um mês, o PowerShell adicionará o número de dias ao mês.</span><span class="sxs-lookup"><span data-stu-id="d5625-190">If the specified value is greater than the number of days in a month, PowerShell adds the number of days to the month.</span></span> <span data-ttu-id="d5625-191">Por exemplo, `Get-Date -Month 2 -Day 31` exibe **3 de março**, não **31 de fevereiro**.</span><span class="sxs-lookup"><span data-stu-id="d5625-191">For example, `Get-Date -Month 2 -Day 31` displays **March 3**, not **February 31**.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5625-192">-DisplayHint</span><span class="sxs-lookup"><span data-stu-id="d5625-192">-DisplayHint</span></span>

<span data-ttu-id="d5625-193">Determina quais elementos de data e hora são exibidos.</span><span class="sxs-lookup"><span data-stu-id="d5625-193">Determines which elements of the date and time are displayed.</span></span>

<span data-ttu-id="d5625-194">Os valores aceitos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="d5625-194">The accepted values are as follows:</span></span>

- <span data-ttu-id="d5625-195">**Data**: exibe somente a data</span><span class="sxs-lookup"><span data-stu-id="d5625-195">**Date**: displays only the date</span></span>
- <span data-ttu-id="d5625-196">**Hora**: exibe apenas a hora</span><span class="sxs-lookup"><span data-stu-id="d5625-196">**Time**: displays only the time</span></span>
- <span data-ttu-id="d5625-197">**DateTime**: exibe a data e a hora</span><span class="sxs-lookup"><span data-stu-id="d5625-197">**DateTime**: displays the date and time</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.DisplayHintType
Parameter Sets: (All)
Aliases:
Accepted values: Date, Time, DateTime

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5625-198">-Formato</span><span class="sxs-lookup"><span data-stu-id="d5625-198">-Format</span></span>

<span data-ttu-id="d5625-199">Exibe a data e hora no formato do Microsoft .NET Framework indicado pelo especificador de formato.</span><span class="sxs-lookup"><span data-stu-id="d5625-199">Displays the date and time in the Microsoft .NET Framework format indicated by the format specifier.</span></span>
<span data-ttu-id="d5625-200">O parâmetro **Format** gera um objeto **String** .</span><span class="sxs-lookup"><span data-stu-id="d5625-200">The **Format** parameter outputs a **String** object.</span></span>

<span data-ttu-id="d5625-201">Para obter uma lista de especificadores de formato .NET disponíveis, consulte [cadeias de caracteres de formato personalizado de data e hora](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span><span class="sxs-lookup"><span data-stu-id="d5625-201">For a list of available .NET format specifiers, see [Custom date and time format strings](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span></span>

<span data-ttu-id="d5625-202">Quando o parâmetro **Format** é usado, `Get-Date` obtém apenas as propriedades do objeto **DateTime** necessárias para exibir a data.</span><span class="sxs-lookup"><span data-stu-id="d5625-202">When the **Format** parameter is used, `Get-Date` only gets the **DateTime** object's properties necessary to display the date.</span></span> <span data-ttu-id="d5625-203">Como resultado, algumas das propriedades e métodos de objetos **DateTime** podem não estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d5625-203">As a result, some of the properties and methods of **DateTime** objects might not be available.</span></span>

<span data-ttu-id="d5625-204">A partir do PowerShell 5,0, você pode usar os seguintes formatos adicionais como valores para o parâmetro de **formato** .</span><span class="sxs-lookup"><span data-stu-id="d5625-204">Starting in PowerShell 5.0, you can use the following additional formats as values for the **Format** parameter.</span></span>

- <span data-ttu-id="d5625-205">**Data de início**.</span><span class="sxs-lookup"><span data-stu-id="d5625-205">**FileDate**.</span></span> <span data-ttu-id="d5625-206">Uma representação amigável de arquivo ou caminho da data atual na hora local.</span><span class="sxs-lookup"><span data-stu-id="d5625-206">A file or path-friendly representation of the current date in local time.</span></span> <span data-ttu-id="d5625-207">O formato é `yyyyMMdd` (diferencia maiúsculas de minúsculas, usando um ano de 4 dígitos, um mês de 2 dígitos e um dia de 2 dígitos).</span><span class="sxs-lookup"><span data-stu-id="d5625-207">The format is `yyyyMMdd` (case-sensitive, using a 4-digit year, 2-digit month, and 2-digit day).</span></span> <span data-ttu-id="d5625-208">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d5625-208">For example:</span></span>
  20190627.

- <span data-ttu-id="d5625-209">**FileDateUniversal**.</span><span class="sxs-lookup"><span data-stu-id="d5625-209">**FileDateUniversal**.</span></span> <span data-ttu-id="d5625-210">Uma representação amigável de arquivo ou caminho da data atual em tempo universal (UTC).</span><span class="sxs-lookup"><span data-stu-id="d5625-210">A file or path-friendly representation of the current date in universal time (UTC).</span></span> <span data-ttu-id="d5625-211">O formato é `yyyyMMddZ` (diferencia maiúsculas de minúsculas, usando um ano de 4 dígitos, um mês de 2 dígitos, um dia de 2 dígitos e a letra `Z` como o indicador UTC).</span><span class="sxs-lookup"><span data-stu-id="d5625-211">The format is `yyyyMMddZ` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, and the letter `Z` as the UTC indicator).</span></span> <span data-ttu-id="d5625-212">Por exemplo: 20190627Z.</span><span class="sxs-lookup"><span data-stu-id="d5625-212">For example: 20190627Z.</span></span>

- <span data-ttu-id="d5625-213">**FileDateTime**.</span><span class="sxs-lookup"><span data-stu-id="d5625-213">**FileDateTime**.</span></span> <span data-ttu-id="d5625-214">Uma representação de arquivo ou de caminho amigável da data e hora atuais na hora local, no formato de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="d5625-214">A file or path-friendly representation of the current date and time in local time, in 24-hour format.</span></span> <span data-ttu-id="d5625-215">O formato é `yyyyMMddTHHmmssffff` (diferencia maiúsculas de minúsculas, usando um ano de 4 dígitos, um mês de 2 dígitos, um dia de 2 dígitos, a letra `T` como um separador de hora, hora de 2 dígitos, minuto de 2 dígitos, segundo de 2 dígitos e milissegundo de 4 dígitos).</span><span class="sxs-lookup"><span data-stu-id="d5625-215">The format is `yyyyMMddTHHmmssffff` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, the letter `T` as a time separator, 2-digit hour, 2-digit minute, 2-digit second, and 4-digit millisecond).</span></span> <span data-ttu-id="d5625-216">Por exemplo: 20190627T0840107271.</span><span class="sxs-lookup"><span data-stu-id="d5625-216">For example: 20190627T0840107271.</span></span>

- <span data-ttu-id="d5625-217">**FileDateTimeUniversal**.</span><span class="sxs-lookup"><span data-stu-id="d5625-217">**FileDateTimeUniversal**.</span></span> <span data-ttu-id="d5625-218">Uma representação amigável de arquivo ou caminho da data e hora atuais em UTC (hora universal), no formato de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="d5625-218">A file or path-friendly representation of the current date and time in universal time (UTC), in 24-hour format.</span></span> <span data-ttu-id="d5625-219">O formato é `yyyyMMddTHHmmssffffZ` (diferencia maiúsculas de minúsculas, usando um ano de 4 dígitos, um mês de 2 dígitos, um dia de 2 dígitos, a letra `T` como um separador de hora, hora de 2 dígitos, minuto de 2 dígitos, segundo de 2 dígitos, milissegundo de 4 dígitos e a letra `Z` como o indicador UTC).</span><span class="sxs-lookup"><span data-stu-id="d5625-219">The format is `yyyyMMddTHHmmssffffZ` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, the letter `T` as a time separator, 2-digit hour, 2-digit minute, 2-digit second, 4-digit millisecond, and the letter `Z` as the UTC indicator).</span></span> <span data-ttu-id="d5625-220">Por exemplo: 20190627T1540500718Z.</span><span class="sxs-lookup"><span data-stu-id="d5625-220">For example: 20190627T1540500718Z.</span></span>

```yaml
Type: System.String
Parameter Sets: net
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5625-221">-Hora</span><span class="sxs-lookup"><span data-stu-id="d5625-221">-Hour</span></span>

<span data-ttu-id="d5625-222">Especifica a hora que é exibida.</span><span class="sxs-lookup"><span data-stu-id="d5625-222">Specifies the hour that is displayed.</span></span> <span data-ttu-id="d5625-223">Insira um valor de 0 a 23.</span><span class="sxs-lookup"><span data-stu-id="d5625-223">Enter a value from 0 to 23.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5625-224">-Milissegundo</span><span class="sxs-lookup"><span data-stu-id="d5625-224">-Millisecond</span></span>

<span data-ttu-id="d5625-225">Especifica os milissegundos na data.</span><span class="sxs-lookup"><span data-stu-id="d5625-225">Specifies the milliseconds in the date.</span></span> <span data-ttu-id="d5625-226">Insira um valor de 0 a 999.</span><span class="sxs-lookup"><span data-stu-id="d5625-226">Enter a value from 0 to 999.</span></span>

<span data-ttu-id="d5625-227">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d5625-227">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5625-228">-Minuto</span><span class="sxs-lookup"><span data-stu-id="d5625-228">-Minute</span></span>

<span data-ttu-id="d5625-229">Especifica o minuto que é exibido.</span><span class="sxs-lookup"><span data-stu-id="d5625-229">Specifies the minute that is displayed.</span></span> <span data-ttu-id="d5625-230">Insira um valor de 0 a 59.</span><span class="sxs-lookup"><span data-stu-id="d5625-230">Enter a value from 0 to 59.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5625-231">-Mês</span><span class="sxs-lookup"><span data-stu-id="d5625-231">-Month</span></span>

<span data-ttu-id="d5625-232">Especifica o mês que é exibido.</span><span class="sxs-lookup"><span data-stu-id="d5625-232">Specifies the month that is displayed.</span></span> <span data-ttu-id="d5625-233">Insira um valor de 1 a 12.</span><span class="sxs-lookup"><span data-stu-id="d5625-233">Enter a value from 1 to 12.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5625-234">-Segundo</span><span class="sxs-lookup"><span data-stu-id="d5625-234">-Second</span></span>

<span data-ttu-id="d5625-235">Especifica o segundo que é exibido.</span><span class="sxs-lookup"><span data-stu-id="d5625-235">Specifies the second that is displayed.</span></span> <span data-ttu-id="d5625-236">Insira um valor de 0 a 59.</span><span class="sxs-lookup"><span data-stu-id="d5625-236">Enter a value from 0 to 59.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5625-237">-UFormat</span><span class="sxs-lookup"><span data-stu-id="d5625-237">-UFormat</span></span>

<span data-ttu-id="d5625-238">Exibe a data e hora no formato UNIX.</span><span class="sxs-lookup"><span data-stu-id="d5625-238">Displays the date and time in UNIX format.</span></span> <span data-ttu-id="d5625-239">O parâmetro **uFormat** gera um objeto de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="d5625-239">The **UFormat** parameter outputs a string object.</span></span>

<span data-ttu-id="d5625-240">Os especificadores **uFormat** são precedidos por um sinal de porcentagem ( `%` ), por exemplo,, `%m` `%d` e `%Y` .</span><span class="sxs-lookup"><span data-stu-id="d5625-240">**UFormat** specifiers are preceded by a percent sign (`%`), for example, `%m`, `%d`, and `%Y`.</span></span> <span data-ttu-id="d5625-241">A seção [observações](#notes) contém uma tabela de **especificadores uFormat** válidos.</span><span class="sxs-lookup"><span data-stu-id="d5625-241">The [Notes](#notes) section contains a table of valid **UFormat specifiers**.</span></span>

<span data-ttu-id="d5625-242">Quando o parâmetro **uFormat** é usado, `Get-Date` obtém apenas as propriedades do objeto **DateTime** necessárias para exibir a data.</span><span class="sxs-lookup"><span data-stu-id="d5625-242">When the **UFormat** parameter is used, `Get-Date` only gets the **DateTime** object's properties necessary to display the date.</span></span> <span data-ttu-id="d5625-243">Como resultado, algumas das propriedades e métodos de objetos **DateTime** podem não estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d5625-243">As a result, some of the properties and methods of **DateTime** objects might not be available.</span></span>

```yaml
Type: System.String
Parameter Sets: UFormat
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5625-244">-Ano</span><span class="sxs-lookup"><span data-stu-id="d5625-244">-Year</span></span>

<span data-ttu-id="d5625-245">Especifica o ano que é exibido.</span><span class="sxs-lookup"><span data-stu-id="d5625-245">Specifies the year that is displayed.</span></span> <span data-ttu-id="d5625-246">Insira um valor de 1 a 9999.</span><span class="sxs-lookup"><span data-stu-id="d5625-246">Enter a value from 1 to 9999.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5625-247">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d5625-247">CommonParameters</span></span>

<span data-ttu-id="d5625-248">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d5625-248">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d5625-249">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d5625-249">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d5625-250">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d5625-250">INPUTS</span></span>

### <span data-ttu-id="d5625-251">Entrada de pipeline</span><span class="sxs-lookup"><span data-stu-id="d5625-251">Pipeline input</span></span>

<span data-ttu-id="d5625-252">`Get-Date` aceita a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="d5625-252">`Get-Date` accepts pipeline input.</span></span> <span data-ttu-id="d5625-253">Por exemplo, `Get-ChildItem | Get-Date`.</span><span class="sxs-lookup"><span data-stu-id="d5625-253">For example, `Get-ChildItem | Get-Date`.</span></span>

## <span data-ttu-id="d5625-254">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d5625-254">OUTPUTS</span></span>

### <span data-ttu-id="d5625-255">System. DateTime ou System. String</span><span class="sxs-lookup"><span data-stu-id="d5625-255">System.DateTime or System.String</span></span>

<span data-ttu-id="d5625-256">`Get-Date` Retorna um objeto **DateTime** , exceto quando os parâmetros **Format** e **uFormat** são usados.</span><span class="sxs-lookup"><span data-stu-id="d5625-256">`Get-Date` returns a **DateTime** object except when the **Format** and **UFormat** parameters are used.</span></span> <span data-ttu-id="d5625-257">Os parâmetros **Format** ou **uFormat** retornam objetos de **cadeia de caracteres** .</span><span class="sxs-lookup"><span data-stu-id="d5625-257">The **Format** or **UFormat** parameters return **String** objects.</span></span>

<span data-ttu-id="d5625-258">Quando um objeto **DateTime** é enviado ao pipeline para um cmdlet como o `Add-Content` que espera entrada de cadeia de caracteres, o PowerShell converte o objeto em um objeto de cadeia de **caracteres** .</span><span class="sxs-lookup"><span data-stu-id="d5625-258">When a **DateTime** object is sent down the pipeline to a cmdlet such as `Add-Content` that expects string input, PowerShell converts the object to a **String** object.</span></span>

<span data-ttu-id="d5625-259">O método `(Get-Date).ToString()` converte um objeto **DateTime** em um objeto **String** .</span><span class="sxs-lookup"><span data-stu-id="d5625-259">The method `(Get-Date).ToString()` converts a **DateTime** object a **String** object.</span></span>

<span data-ttu-id="d5625-260">Para exibir as propriedades e os métodos de um objeto, envie o objeto para baixo no pipeline para `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="d5625-260">To display an object's properties and methods, send the object down the pipeline to `Get-Member`.</span></span>
<span data-ttu-id="d5625-261">Por exemplo, `Get-Date | Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="d5625-261">For example, `Get-Date | Get-Member`.</span></span>

## <span data-ttu-id="d5625-262">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d5625-262">NOTES</span></span>

<span data-ttu-id="d5625-263">Os objetos **DateTime** estão em formatos de data e hora longa para a localidade do sistema.</span><span class="sxs-lookup"><span data-stu-id="d5625-263">**DateTime** objects are in long-date and long-time formats for the system locale.</span></span>

<span data-ttu-id="d5625-264">Os **especificadores uFormat** válidos são exibidos na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="d5625-264">The valid **UFormat specifiers** are displayed in the following table:</span></span>

| <span data-ttu-id="d5625-265">Especificador de formato</span><span class="sxs-lookup"><span data-stu-id="d5625-265">Format specifier</span></span> |                                 <span data-ttu-id="d5625-266">Significado</span><span class="sxs-lookup"><span data-stu-id="d5625-266">Meaning</span></span>                     |         <span data-ttu-id="d5625-267">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d5625-267">Example</span></span>          |
| ---- | ----------------------------------------------------------------------- | ------------------------ |
| `%A` | <span data-ttu-id="d5625-268">Dia da semana-nome completo</span><span class="sxs-lookup"><span data-stu-id="d5625-268">Day of the week - full name</span></span>                                             | <span data-ttu-id="d5625-269">Monday</span><span class="sxs-lookup"><span data-stu-id="d5625-269">Monday</span></span>                   |
| `%a` | <span data-ttu-id="d5625-270">Dia da semana-nome abreviado</span><span class="sxs-lookup"><span data-stu-id="d5625-270">Day of the week - abbreviated name</span></span>                                      | <span data-ttu-id="d5625-271">Mon</span><span class="sxs-lookup"><span data-stu-id="d5625-271">Mon</span></span>                      |
| `%B` | <span data-ttu-id="d5625-272">Nome do mês-completo</span><span class="sxs-lookup"><span data-stu-id="d5625-272">Month name - full</span></span>                                                       | <span data-ttu-id="d5625-273">Janeiro</span><span class="sxs-lookup"><span data-stu-id="d5625-273">January</span></span>                  |
| `%b` | <span data-ttu-id="d5625-274">Nome do mês-abreviado</span><span class="sxs-lookup"><span data-stu-id="d5625-274">Month name - abbreviated</span></span>                                                | <span data-ttu-id="d5625-275">Jan</span><span class="sxs-lookup"><span data-stu-id="d5625-275">Jan</span></span>                      |
| `%C` | <span data-ttu-id="d5625-276">Anos</span><span class="sxs-lookup"><span data-stu-id="d5625-276">Century</span></span>                                                                 | <span data-ttu-id="d5625-277">20 para 2019</span><span class="sxs-lookup"><span data-stu-id="d5625-277">20 for 2019</span></span>              |
| `%c` | <span data-ttu-id="d5625-278">Data e hora abreviadas</span><span class="sxs-lookup"><span data-stu-id="d5625-278">Date and time - abbreviated</span></span>                                             | <span data-ttu-id="d5625-279">Quinta-feira-Jun 27 08:44:18 2019</span><span class="sxs-lookup"><span data-stu-id="d5625-279">Thu Jun 27 08:44:18 2019</span></span> |
| `%D` | <span data-ttu-id="d5625-280">Data no formato mm/dd/aa</span><span class="sxs-lookup"><span data-stu-id="d5625-280">Date in mm/dd/yy format</span></span>                                                 | <span data-ttu-id="d5625-281">06/27/19</span><span class="sxs-lookup"><span data-stu-id="d5625-281">06/27/19</span></span>                 |
| `%d` | <span data-ttu-id="d5625-282">Dia do mês-2 dígitos</span><span class="sxs-lookup"><span data-stu-id="d5625-282">Day of the month - 2 digits</span></span>                                             | <span data-ttu-id="d5625-283">05</span><span class="sxs-lookup"><span data-stu-id="d5625-283">05</span></span>                       |
| `%e` | <span data-ttu-id="d5625-284">Dia do mês-precedido por um espaço se houver apenas um único dígito</span><span class="sxs-lookup"><span data-stu-id="d5625-284">Day of the month - preceded by a space if only a single digit</span></span>           | <span data-ttu-id="d5625-285">\<space\>05</span><span class="sxs-lookup"><span data-stu-id="d5625-285">\<space\>5</span></span>               |
| `%F` | <span data-ttu-id="d5625-286">Data no formato aaaa-mm-dd, igual a% Y-% m-% d (o formato de data ISO 8601)</span><span class="sxs-lookup"><span data-stu-id="d5625-286">Date in YYYY-mm-dd format, equal to %Y-%m-%d (the ISO 8601 date format)</span></span> | <span data-ttu-id="d5625-287">2019-06-27</span><span class="sxs-lookup"><span data-stu-id="d5625-287">2019-06-27</span></span>               |
| `%G` | <span data-ttu-id="d5625-288">O mesmo que ' Y '</span><span class="sxs-lookup"><span data-stu-id="d5625-288">Same as 'Y'</span></span>                                                             |                          |
| `%g` | <span data-ttu-id="d5625-289">O mesmo que ' y '</span><span class="sxs-lookup"><span data-stu-id="d5625-289">Same as 'y'</span></span>                                                             |                          |
| `%H` | <span data-ttu-id="d5625-290">Hora no formato de 24 horas</span><span class="sxs-lookup"><span data-stu-id="d5625-290">Hour in 24-hour format</span></span>                                                  | <span data-ttu-id="d5625-291">17</span><span class="sxs-lookup"><span data-stu-id="d5625-291">17</span></span>                       |
| `%h` | <span data-ttu-id="d5625-292">Mesmo que ' b '</span><span class="sxs-lookup"><span data-stu-id="d5625-292">Same as 'b'</span></span>                                                             |                          |
| `%I` | <span data-ttu-id="d5625-293">Hora no formato de 12 horas</span><span class="sxs-lookup"><span data-stu-id="d5625-293">Hour in 12-hour format</span></span>                                                  | <span data-ttu-id="d5625-294">05</span><span class="sxs-lookup"><span data-stu-id="d5625-294">05</span></span>                       |
| `%j` | <span data-ttu-id="d5625-295">Dia do ano</span><span class="sxs-lookup"><span data-stu-id="d5625-295">Day of the year</span></span>                                                         | <span data-ttu-id="d5625-296">1-366</span><span class="sxs-lookup"><span data-stu-id="d5625-296">1-366</span></span>                    |
| `%k` | <span data-ttu-id="d5625-297">Mesmo que ' H '</span><span class="sxs-lookup"><span data-stu-id="d5625-297">Same as 'H'</span></span>                                                             |                          |
| `%l` | <span data-ttu-id="d5625-298">O mesmo que ' I ' (I maiúsculo)</span><span class="sxs-lookup"><span data-stu-id="d5625-298">Same as 'I' (Upper-case I)</span></span>                                              | <span data-ttu-id="d5625-299">05</span><span class="sxs-lookup"><span data-stu-id="d5625-299">05</span></span>                       |
| `%M` | <span data-ttu-id="d5625-300">minutos</span><span class="sxs-lookup"><span data-stu-id="d5625-300">Minutes</span></span>                                                                 | <span data-ttu-id="d5625-301">35</span><span class="sxs-lookup"><span data-stu-id="d5625-301">35</span></span>                       |
| `%m` | <span data-ttu-id="d5625-302">Número do mês</span><span class="sxs-lookup"><span data-stu-id="d5625-302">Month number</span></span>                                                            | <span data-ttu-id="d5625-303">06</span><span class="sxs-lookup"><span data-stu-id="d5625-303">06</span></span>                       |
| `%n` | <span data-ttu-id="d5625-304">caractere de nova linha</span><span class="sxs-lookup"><span data-stu-id="d5625-304">newline character</span></span>                                                       |                          |
| `%p` | <span data-ttu-id="d5625-305">AM ou PM</span><span class="sxs-lookup"><span data-stu-id="d5625-305">AM or PM</span></span>                                                                |                          |
| `%R` | <span data-ttu-id="d5625-306">Tempo no formato de 24 horas-sem segundos</span><span class="sxs-lookup"><span data-stu-id="d5625-306">Time in 24-hour format -no seconds</span></span>                                      | <span data-ttu-id="d5625-307">17:45</span><span class="sxs-lookup"><span data-stu-id="d5625-307">17:45</span></span>                    |
| `%r` | <span data-ttu-id="d5625-308">Hora no formato de 12 horas</span><span class="sxs-lookup"><span data-stu-id="d5625-308">Time in 12-hour format</span></span>                                                  | <span data-ttu-id="d5625-309">09:15:36 AM</span><span class="sxs-lookup"><span data-stu-id="d5625-309">09:15:36 AM</span></span>              |
| `%S` | <span data-ttu-id="d5625-310">Segundos</span><span class="sxs-lookup"><span data-stu-id="d5625-310">Seconds</span></span>                                                                 | <span data-ttu-id="d5625-311">05</span><span class="sxs-lookup"><span data-stu-id="d5625-311">05</span></span>                       |
| `%s` | <span data-ttu-id="d5625-312">Segundos decorridos desde 1º de janeiro de 1970 00:00:00</span><span class="sxs-lookup"><span data-stu-id="d5625-312">Seconds elapsed since January 1, 1970 00:00:00</span></span>                          | <span data-ttu-id="d5625-313">1150451174</span><span class="sxs-lookup"><span data-stu-id="d5625-313">1150451174</span></span>               |
| `%t` | <span data-ttu-id="d5625-314">Caractere de tabulação horizontal</span><span class="sxs-lookup"><span data-stu-id="d5625-314">Horizontal tab character</span></span>                                                |                          |
| `%T` | <span data-ttu-id="d5625-315">Tempo no formato de 24 horas</span><span class="sxs-lookup"><span data-stu-id="d5625-315">Time in 24-hour format</span></span>                                                  | <span data-ttu-id="d5625-316">17:45:52</span><span class="sxs-lookup"><span data-stu-id="d5625-316">17:45:52</span></span>                 |
| `%U` | <span data-ttu-id="d5625-317">Mesmo que ' W '</span><span class="sxs-lookup"><span data-stu-id="d5625-317">Same as 'W'</span></span>                                                             |                          |
| `%u` | <span data-ttu-id="d5625-318">Dia da semana-número</span><span class="sxs-lookup"><span data-stu-id="d5625-318">Day of the week - number</span></span>                                                | <span data-ttu-id="d5625-319">Domingo = 0</span><span class="sxs-lookup"><span data-stu-id="d5625-319">Sunday = 0</span></span>               |
| `%V` | <span data-ttu-id="d5625-320">Semana do ano</span><span class="sxs-lookup"><span data-stu-id="d5625-320">Week of the year</span></span>                                                        | <span data-ttu-id="d5625-321">01-53</span><span class="sxs-lookup"><span data-stu-id="d5625-321">01-53</span></span>                    |
| `%w` | <span data-ttu-id="d5625-322">Mesmo que ' u '</span><span class="sxs-lookup"><span data-stu-id="d5625-322">Same as 'u'</span></span>                                                             |                          |
| `%W` | <span data-ttu-id="d5625-323">Semana do ano</span><span class="sxs-lookup"><span data-stu-id="d5625-323">Week of the year</span></span>                                                        | <span data-ttu-id="d5625-324">00-52</span><span class="sxs-lookup"><span data-stu-id="d5625-324">00-52</span></span>                    |
| `%X` | <span data-ttu-id="d5625-325">Igual a ' T'</span><span class="sxs-lookup"><span data-stu-id="d5625-325">Same as 'T'</span></span>                                                             |                          |
| `%x` | <span data-ttu-id="d5625-326">Data no formato padrão para localidade</span><span class="sxs-lookup"><span data-stu-id="d5625-326">Date in standard format for locale</span></span>                                      | <span data-ttu-id="d5625-327">06/27/19 para inglês-EUA</span><span class="sxs-lookup"><span data-stu-id="d5625-327">06/27/19 for English-US</span></span>  |
| `%Y` | <span data-ttu-id="d5625-328">Ano no formato de 4 dígitos</span><span class="sxs-lookup"><span data-stu-id="d5625-328">Year in 4-digit format</span></span>                                                  | <span data-ttu-id="d5625-329">2019</span><span class="sxs-lookup"><span data-stu-id="d5625-329">2019</span></span>                     |
| `%y` | <span data-ttu-id="d5625-330">Ano no formato de 2 dígitos</span><span class="sxs-lookup"><span data-stu-id="d5625-330">Year in 2-digit format</span></span>                                                  | <span data-ttu-id="d5625-331">19</span><span class="sxs-lookup"><span data-stu-id="d5625-331">19</span></span>                       |
| `%Z` | <span data-ttu-id="d5625-332">Deslocamento de fuso horário da coordenada de tempo universal (UTC)</span><span class="sxs-lookup"><span data-stu-id="d5625-332">Time zone offset from Universal Time Coordinate (UTC)</span></span>                   | <span data-ttu-id="d5625-333">-07</span><span class="sxs-lookup"><span data-stu-id="d5625-333">-07</span></span>                      |

## <span data-ttu-id="d5625-334">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d5625-334">RELATED LINKS</span></span>

[<span data-ttu-id="d5625-335">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="d5625-335">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="d5625-336">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="d5625-336">Get-Culture</span></span>](Get-Culture.md)

[<span data-ttu-id="d5625-337">Get-Member</span><span class="sxs-lookup"><span data-stu-id="d5625-337">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="d5625-338">New-Item</span><span class="sxs-lookup"><span data-stu-id="d5625-338">New-Item</span></span>](../Microsoft.PowerShell.Management/New-Item.md)

[<span data-ttu-id="d5625-339">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="d5625-339">New-TimeSpan</span></span>](New-TimeSpan.md)

[<span data-ttu-id="d5625-340">Set-Date</span><span class="sxs-lookup"><span data-stu-id="d5625-340">Set-Date</span></span>](Set-Date.md)
