---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Date
ms.openlocfilehash: 6f5c76faafa2c68a6d9dfc604238c514489aa717
ms.sourcegitcommit: 3a1d80e27438976101f216b8c3d623c61b868db8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "99975049"
---
# <span data-ttu-id="9de3b-102">Get-Date</span><span class="sxs-lookup"><span data-stu-id="9de3b-102">Get-Date</span></span>

## <span data-ttu-id="9de3b-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="9de3b-103">SYNOPSIS</span></span>
<span data-ttu-id="9de3b-104">Obtém a data e hora atuais.</span><span class="sxs-lookup"><span data-stu-id="9de3b-104">Gets the current date and time.</span></span>

## <span data-ttu-id="9de3b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9de3b-105">SYNTAX</span></span>

### <span data-ttu-id="9de3b-106">Data (padrão)</span><span class="sxs-lookup"><span data-stu-id="9de3b-106">Date (Default)</span></span>

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-Format <String>] [-AsUTC] [<CommonParameters>]
```

### <span data-ttu-id="9de3b-107">DateUFormat</span><span class="sxs-lookup"><span data-stu-id="9de3b-107">DateUFormat</span></span>

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 -UFormat <String> [<CommonParameters>]
```

### <span data-ttu-id="9de3b-108">UnixTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="9de3b-108">UnixTimeSeconds</span></span>

```
Get-Date -UnixTimeSeconds <Int64> [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-Format <String>] [-AsUTC] [<CommonParameters>]
```

### <span data-ttu-id="9de3b-109">UnixTimeSecondsUFormat</span><span class="sxs-lookup"><span data-stu-id="9de3b-109">UnixTimeSecondsUFormat</span></span>

```
Get-Date -UnixTimeSeconds <Int64> [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 -UFormat <String> [<CommonParameters>]
```

## <span data-ttu-id="9de3b-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9de3b-110">DESCRIPTION</span></span>

<span data-ttu-id="9de3b-111">O `Get-Date` cmdlet obtém um objeto **DateTime** que representa a data atual ou uma data que você especifica.</span><span class="sxs-lookup"><span data-stu-id="9de3b-111">The `Get-Date` cmdlet gets a **DateTime** object that represents the current date or a date that you specify.</span></span> <span data-ttu-id="9de3b-112">`Get-Date` pode formatar a data e a hora em vários formatos .NET e UNIX.</span><span class="sxs-lookup"><span data-stu-id="9de3b-112">`Get-Date` can format the date and time in several .NET and UNIX formats.</span></span> <span data-ttu-id="9de3b-113">Você pode usar `Get-Date` para gerar uma cadeia de caracteres de caractere de data ou hora e, em seguida, enviar a cadeia de caracteres para outros cmdlets ou programas.</span><span class="sxs-lookup"><span data-stu-id="9de3b-113">You can use `Get-Date` to generate a date or time character string, and then send the string to other cmdlets or programs.</span></span>

<span data-ttu-id="9de3b-114">`Get-Date` usa as configurações de cultura do computador para determinar como a saída é formatada.</span><span class="sxs-lookup"><span data-stu-id="9de3b-114">`Get-Date` uses the computer's culture settings to determine how the output is formatted.</span></span> <span data-ttu-id="9de3b-115">Para exibir as configurações do computador, use `(Get-Culture).DateTimeFormat` .</span><span class="sxs-lookup"><span data-stu-id="9de3b-115">To view your computer's settings, use `(Get-Culture).DateTimeFormat`.</span></span>

## <span data-ttu-id="9de3b-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="9de3b-116">EXAMPLES</span></span>

### <span data-ttu-id="9de3b-117">Exemplo 1: obter a data e a hora atuais</span><span class="sxs-lookup"><span data-stu-id="9de3b-117">Example 1: Get the current date and time</span></span>

<span data-ttu-id="9de3b-118">Neste exemplo, `Get-Date` exibe a data e hora atuais do sistema.</span><span class="sxs-lookup"><span data-stu-id="9de3b-118">In this example, `Get-Date` displays the current system date and time.</span></span> <span data-ttu-id="9de3b-119">A saída está nos formatos de longa data e de hora longa.</span><span class="sxs-lookup"><span data-stu-id="9de3b-119">The output is in the long-date and long-time formats.</span></span>

```powershell
Get-Date
```

```Output
Tuesday, June 25, 2019 14:53:32
```

### <span data-ttu-id="9de3b-120">Exemplo 2: obter elementos da data e hora atuais</span><span class="sxs-lookup"><span data-stu-id="9de3b-120">Example 2: Get elements of the current date and time</span></span>

<span data-ttu-id="9de3b-121">Este exemplo mostra como usar `Get-Date` para obter o elemento Date ou time.</span><span class="sxs-lookup"><span data-stu-id="9de3b-121">This example shows how to use `Get-Date` to get either the date or time element.</span></span> <span data-ttu-id="9de3b-122">O parâmetro usa os argumentos **Date**, **time** ou **DateTime**.</span><span class="sxs-lookup"><span data-stu-id="9de3b-122">The parameter uses the arguments **Date**, **Time**, or **DateTime**.</span></span>

```powershell
Get-Date -DisplayHint Date
```

```Output
Tuesday, June 25, 2019
```

<span data-ttu-id="9de3b-123">`Get-Date` usa o parâmetro **DisplayHint** com o argumento **Date** para obter apenas a data.</span><span class="sxs-lookup"><span data-stu-id="9de3b-123">`Get-Date` uses the **DisplayHint** parameter with the **Date** argument to get only the date.</span></span>

### <span data-ttu-id="9de3b-124">Exemplo 3: obter a data e a hora com um especificador de formato .NET</span><span class="sxs-lookup"><span data-stu-id="9de3b-124">Example 3: Get the date and time with a .NET format specifier</span></span>

<span data-ttu-id="9de3b-125">Neste exemplo, um especificador de formato .NET é usado para personalizar o formato da saída.</span><span class="sxs-lookup"><span data-stu-id="9de3b-125">In this example, a .NET format specifier is used to customize the output's format.</span></span> <span data-ttu-id="9de3b-126">A saída é um objeto de **cadeia de caracteres** .</span><span class="sxs-lookup"><span data-stu-id="9de3b-126">The output is a **String** object.</span></span>

```powershell
Get-Date -Format "dddd MM/dd/yyyy HH:mm K"
```

```Output
Tuesday 06/25/2019 16:17 -07:00
```

<span data-ttu-id="9de3b-127">`Get-Date` usa o parâmetro **Format** para especificar vários especificadores de formato.</span><span class="sxs-lookup"><span data-stu-id="9de3b-127">`Get-Date` uses the **Format** parameter to specify several format specifiers.</span></span>

<span data-ttu-id="9de3b-128">Os especificadores de formato .NET usados neste exemplo são definidos da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="9de3b-128">The .NET format specifiers used in this example are defined as follows:</span></span>

| <span data-ttu-id="9de3b-129">Especificador</span><span class="sxs-lookup"><span data-stu-id="9de3b-129">Specifier</span></span> |                      <span data-ttu-id="9de3b-130">Definição</span><span class="sxs-lookup"><span data-stu-id="9de3b-130">Definition</span></span>                       |
| --------- | ----------------------------------------------------- |
| `dddd`    | <span data-ttu-id="9de3b-131">Dia da semana-nome completo</span><span class="sxs-lookup"><span data-stu-id="9de3b-131">Day of the week - full name</span></span>                           |
| `MM`      | <span data-ttu-id="9de3b-132">Número do mês</span><span class="sxs-lookup"><span data-stu-id="9de3b-132">Month number</span></span>                                          |
| `dd`      | <span data-ttu-id="9de3b-133">Dia do mês-2 dígitos</span><span class="sxs-lookup"><span data-stu-id="9de3b-133">Day of the month - 2 digits</span></span>                           |
| `yyyy`    | <span data-ttu-id="9de3b-134">Ano no formato de 4 dígitos</span><span class="sxs-lookup"><span data-stu-id="9de3b-134">Year in 4-digit format</span></span>                                |
| `HH:mm`   | <span data-ttu-id="9de3b-135">Tempo no formato de 24 horas-sem segundos</span><span class="sxs-lookup"><span data-stu-id="9de3b-135">Time in 24-hour format - no seconds</span></span>                    |
| `K`       | <span data-ttu-id="9de3b-136">Deslocamento de fuso horário da coordenada de tempo universal (UTC)</span><span class="sxs-lookup"><span data-stu-id="9de3b-136">Time zone offset from Universal Time Coordinate (UTC)</span></span> |

<span data-ttu-id="9de3b-137">Para obter mais informações sobre especificadores de formato .NET, consulte [cadeias de caracteres de formato personalizado de data e hora](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span><span class="sxs-lookup"><span data-stu-id="9de3b-137">For more information about .NET format specifiers, see [Custom date and time format strings](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span></span>

### <span data-ttu-id="9de3b-138">Exemplo 4: obter a data e a hora com um especificador UFormat</span><span class="sxs-lookup"><span data-stu-id="9de3b-138">Example 4: Get the date and time with a UFormat specifier</span></span>

<span data-ttu-id="9de3b-139">Neste exemplo, vários especificadores de formato **uFormat** são usados para personalizar o formato da saída.</span><span class="sxs-lookup"><span data-stu-id="9de3b-139">In this example, several **UFormat** format specifiers are used to customize the output's format.</span></span>
<span data-ttu-id="9de3b-140">A saída é um objeto de **cadeia de caracteres** .</span><span class="sxs-lookup"><span data-stu-id="9de3b-140">The output is a **String** object.</span></span>

```powershell
Get-Date -UFormat "%A %m/%d/%Y %R %Z"
```

```Output
Tuesday 06/25/2019 16:19 -07
```

<span data-ttu-id="9de3b-141">`Get-Date` usa o parâmetro **uFormat** para especificar vários especificadores de formato.</span><span class="sxs-lookup"><span data-stu-id="9de3b-141">`Get-Date` uses the **UFormat** parameter to specify several format specifiers.</span></span>

<span data-ttu-id="9de3b-142">Os especificadores de formato **uFormat** usados neste exemplo são definidos da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="9de3b-142">The **UFormat** format specifiers used in this example are defined as follows:</span></span>

| <span data-ttu-id="9de3b-143">Especificador</span><span class="sxs-lookup"><span data-stu-id="9de3b-143">Specifier</span></span> |                      <span data-ttu-id="9de3b-144">Definição</span><span class="sxs-lookup"><span data-stu-id="9de3b-144">Definition</span></span>                       |
| --------- | ----------------------------------------------------- |
| `%A`      | <span data-ttu-id="9de3b-145">Dia da semana-nome completo</span><span class="sxs-lookup"><span data-stu-id="9de3b-145">Day of the week - full name</span></span>                           |
| `%m`      | <span data-ttu-id="9de3b-146">Número do mês</span><span class="sxs-lookup"><span data-stu-id="9de3b-146">Month number</span></span>                                          |
| `%d`      | <span data-ttu-id="9de3b-147">Dia do mês-2 dígitos</span><span class="sxs-lookup"><span data-stu-id="9de3b-147">Day of the month - 2 digits</span></span>                           |
| `%Y`      | <span data-ttu-id="9de3b-148">Ano no formato de 4 dígitos</span><span class="sxs-lookup"><span data-stu-id="9de3b-148">Year in 4-digit format</span></span>                                |
| `%R`      | <span data-ttu-id="9de3b-149">Tempo no formato de 24 horas-sem segundos</span><span class="sxs-lookup"><span data-stu-id="9de3b-149">Time in 24-hour format - no seconds</span></span>                    |
| `%Z`      | <span data-ttu-id="9de3b-150">Deslocamento de fuso horário da coordenada de tempo universal (UTC)</span><span class="sxs-lookup"><span data-stu-id="9de3b-150">Time zone offset from Universal Time Coordinate (UTC)</span></span> |

<span data-ttu-id="9de3b-151">Para obter uma lista de especificadores de formato **uFormat** válidos, consulte a seção [observações](#notes) .</span><span class="sxs-lookup"><span data-stu-id="9de3b-151">For a list of valid **UFormat** format specifiers, see the [Notes](#notes) section.</span></span>

### <span data-ttu-id="9de3b-152">Exemplo 5: obter o dia do ano de uma data</span><span class="sxs-lookup"><span data-stu-id="9de3b-152">Example 5: Get a date's day of the year</span></span>

<span data-ttu-id="9de3b-153">Neste exemplo, uma propriedade é usada para obter o dia numérico do ano.</span><span class="sxs-lookup"><span data-stu-id="9de3b-153">In this example, a property is used to get the numeric day of the year.</span></span>

<span data-ttu-id="9de3b-154">O calendário gregoriano tem 365 dias, exceto os anos bissextos que têm 366 dias.</span><span class="sxs-lookup"><span data-stu-id="9de3b-154">The Gregorian calendar has 365 days, except for leap years that have 366 days.</span></span> <span data-ttu-id="9de3b-155">Por exemplo, 31 de dezembro de 2020 é o dia 366.</span><span class="sxs-lookup"><span data-stu-id="9de3b-155">For example, December 31, 2020 is day 366.</span></span>

```powershell
(Get-Date -Year 2020 -Month 12 -Day 31).DayOfYear
```

```Output
366
```

<span data-ttu-id="9de3b-156">`Get-Date` usa três parâmetros para especificar a data: **ano**, **mês** e **dia**.</span><span class="sxs-lookup"><span data-stu-id="9de3b-156">`Get-Date` uses three parameters to specify the date: **Year**, **Month**, and **Day**.</span></span> <span data-ttu-id="9de3b-157">O comando é encapsulado com parênteses para que o resultado seja avaliado pela propriedade **DayofYear** .</span><span class="sxs-lookup"><span data-stu-id="9de3b-157">The command is wrapped with parentheses so that the result is evaluated by the **DayofYear** property.</span></span>

### <span data-ttu-id="9de3b-158">Exemplo 6: verificar se uma data está ajustada para o horário de verão</span><span class="sxs-lookup"><span data-stu-id="9de3b-158">Example 6: Check if a date is adjusted for daylight savings time</span></span>

<span data-ttu-id="9de3b-159">Este exemplo usa um método booliano para verificar se uma data é ajustada pelo horário de verão.</span><span class="sxs-lookup"><span data-stu-id="9de3b-159">This example uses a boolean method to verify if a date is adjusted by daylight savings time.</span></span>

```powershell
$DST = Get-Date
$DST.IsDaylightSavingTime()
```

```Output
True
```

<span data-ttu-id="9de3b-160">Uma variável, `$DST` armazena o resultado de `Get-Date` .</span><span class="sxs-lookup"><span data-stu-id="9de3b-160">A variable, `$DST` stores the result of `Get-Date`.</span></span> <span data-ttu-id="9de3b-161">`$DST` usa o método **IsDaylightSavingTime** para testar se a data é ajustada para o horário de verão.</span><span class="sxs-lookup"><span data-stu-id="9de3b-161">`$DST` uses the **IsDaylightSavingTime** method to test if the date is adjusted for daylight savings time.</span></span>

### <span data-ttu-id="9de3b-162">Exemplo 7: converter a hora atual em hora UTC</span><span class="sxs-lookup"><span data-stu-id="9de3b-162">Example 7: Convert the current time to UTC time</span></span>

<span data-ttu-id="9de3b-163">Neste exemplo, a hora atual é convertida em hora UTC.</span><span class="sxs-lookup"><span data-stu-id="9de3b-163">In this example, the current time is converted to UTC time.</span></span> <span data-ttu-id="9de3b-164">O deslocamento UTC para a localidade do sistema é usado para converter a hora.</span><span class="sxs-lookup"><span data-stu-id="9de3b-164">The UTC offset for the system's locale is used to convert the time.</span></span> <span data-ttu-id="9de3b-165">Uma tabela na seção [observações](#notes) lista os especificadores de formato **uFormat** válidos.</span><span class="sxs-lookup"><span data-stu-id="9de3b-165">A table in the [Notes](#notes) section lists the valid **UFormat** format specifiers.</span></span>

```powershell
Get-Date -UFormat "%A %B/%d/%Y %T %Z"
$Time = Get-Date
$Time.ToUniversalTime()
```

```Output
Wednesday June/26/2019 10:45:26 -07

Wednesday, June 26, 2019 17:45:26
```

<span data-ttu-id="9de3b-166">`Get-Date` usa o parâmetro **uFormat** com especificadores de formato para exibir a data e a hora atuais do sistema.</span><span class="sxs-lookup"><span data-stu-id="9de3b-166">`Get-Date` uses the **UFormat** parameter with format specifiers to display the current system date and time.</span></span> <span data-ttu-id="9de3b-167">O especificador de formato **% Z** representa o deslocamento UTC de **-07**.</span><span class="sxs-lookup"><span data-stu-id="9de3b-167">The format specifier **%Z** represents the UTC offset of **-07**.</span></span>

<span data-ttu-id="9de3b-168">A `$Time` variável armazena a data e a hora atuais do sistema.</span><span class="sxs-lookup"><span data-stu-id="9de3b-168">The `$Time` variable stores the current system date and time.</span></span> <span data-ttu-id="9de3b-169">`$Time` usa o método **ToUniversalTime ()** para converter a hora com base no deslocamento UTC do computador.</span><span class="sxs-lookup"><span data-stu-id="9de3b-169">`$Time` uses the **ToUniversalTime()** method to convert the time based on the computer's UTC offset.</span></span>

### <span data-ttu-id="9de3b-170">Exemplo 8: criar um carimbo de data/hora</span><span class="sxs-lookup"><span data-stu-id="9de3b-170">Example 8: Create a timestamp</span></span>

<span data-ttu-id="9de3b-171">Neste exemplo, um especificador de formato cria um objeto de **cadeia de caracteres** de carimbo de data/hora para um nome de diretório.</span><span class="sxs-lookup"><span data-stu-id="9de3b-171">In this example, a format specifier creates a timestamp **String** object for a directory name.</span></span> <span data-ttu-id="9de3b-172">O timestamp inclui a data, a hora e o deslocamento UTC.</span><span class="sxs-lookup"><span data-stu-id="9de3b-172">The timestamp includes the date, time, and UTC offset.</span></span>

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

<span data-ttu-id="9de3b-173">A `$timestamp` variável armazena os resultados de um `Get-Date` comando.</span><span class="sxs-lookup"><span data-stu-id="9de3b-173">The `$timestamp` variable stores the results of a `Get-Date` command.</span></span> <span data-ttu-id="9de3b-174">`Get-Date` usa o parâmetro **Format** com o especificador de formato de minúsculas `o` para criar um objeto de **cadeia de caracteres** de carimbo de data/hora.</span><span class="sxs-lookup"><span data-stu-id="9de3b-174">`Get-Date` uses the **Format** parameter with the format specifier of lowercase `o` to create a timestamp **String** object.</span></span> <span data-ttu-id="9de3b-175">O objeto é enviado ao pipeline para `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="9de3b-175">The object is sent down the pipeline to `ForEach-Object`.</span></span> <span data-ttu-id="9de3b-176">Um **scriptblock** contém a `$_` variável que representa o objeto de pipeline atual.</span><span class="sxs-lookup"><span data-stu-id="9de3b-176">A **ScriptBlock** contains the `$_` variable that represents the current pipeline object.</span></span> <span data-ttu-id="9de3b-177">A cadeia de caracteres de carimbo de data/hora é delimitada por dois-pontos que são substituídos por pontos.</span><span class="sxs-lookup"><span data-stu-id="9de3b-177">The timestamp string is delimited by colons that are replaced by periods.</span></span>

<span data-ttu-id="9de3b-178">`New-Item` usa o parâmetro **path** para especificar o local de um novo diretório.</span><span class="sxs-lookup"><span data-stu-id="9de3b-178">`New-Item` uses the **Path** parameter to specify the location for a new directory.</span></span> <span data-ttu-id="9de3b-179">O caminho inclui a `$timestamp` variável como o nome do diretório.</span><span class="sxs-lookup"><span data-stu-id="9de3b-179">The path includes the `$timestamp` variable as the directory name.</span></span> <span data-ttu-id="9de3b-180">O parâmetro de **tipo** especifica que um diretório é criado.</span><span class="sxs-lookup"><span data-stu-id="9de3b-180">The **Type** parameter specifies that a directory is created.</span></span>

### <span data-ttu-id="9de3b-181">Exemplo 9: converter um carimbo de data/hora UNIX</span><span class="sxs-lookup"><span data-stu-id="9de3b-181">Example 9: Convert a Unix timestamp</span></span>

<span data-ttu-id="9de3b-182">Esse exemplo converte o horário do Unix (representado pelo número de segundos desde 1970-01-01 0:00:00) para DateTime.</span><span class="sxs-lookup"><span data-stu-id="9de3b-182">This example converts a Unix time (represented by the number of seconds since 1970-01-01 0:00:00) to DateTime.</span></span>

```powershell
Get-Date -UnixTimeSeconds 1577836800
```

```Output
Wednesday, January 01, 2020 12:00:00 AM
```

### <span data-ttu-id="9de3b-183">Exemplo 10: retornar um valor de data interpretado como UTC</span><span class="sxs-lookup"><span data-stu-id="9de3b-183">Example 10: Return a date value interpreted as UTC</span></span>

<span data-ttu-id="9de3b-184">Este exemplo mostra como interpretar um valor de data como seu equivalente UTC.</span><span class="sxs-lookup"><span data-stu-id="9de3b-184">This example shows how to interpret a date value as its UTC equivalent.</span></span> <span data-ttu-id="9de3b-185">Para o exemplo, essa máquina é definida como **hora padrão do Pacífico**.</span><span class="sxs-lookup"><span data-stu-id="9de3b-185">For the example, this machine is set to **Pacific Standard Time**.</span></span> <span data-ttu-id="9de3b-186">Por padrão, `Get-Date` retorna valores para esse fuso horário.</span><span class="sxs-lookup"><span data-stu-id="9de3b-186">By default, `Get-Date` returns values for that timezone.</span></span> <span data-ttu-id="9de3b-187">Use o parâmetro **AsUTC** para converter o valor para a hora equivalente UTC.</span><span class="sxs-lookup"><span data-stu-id="9de3b-187">Use the **AsUTC** parameter to convert the value to the UTC equivalent time.</span></span>

```powershell
PS> Get-TimeZone

Id                         : Pacific Standard Time
DisplayName                : (UTC-08:00) Pacific Time (US & Canada)
StandardName               : Pacific Standard Time
DaylightName               : Pacific Daylight Time
BaseUtcOffset              : -08:00:00
SupportsDaylightSavingTime : True

PS> (Get-Date -Date "2020-01-01T00:00:00").Kind
Unspecified

PS> Get-Date -Date "2020-01-01T00:00:00"

Wednesday, January 1, 2020 12:00:00 AM

PS> (Get-Date -Date "2020-01-01T00:00:00" -AsUTC).Kind
Utc

PS> Get-Date -Date "2020-01-01T00:00:00" -AsUTC

Wednesday, January 1, 2020 8:00:00 AM
```

## <span data-ttu-id="9de3b-188">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9de3b-188">PARAMETERS</span></span>

### <span data-ttu-id="9de3b-189">-AsUTC</span><span class="sxs-lookup"><span data-stu-id="9de3b-189">-AsUTC</span></span>

<span data-ttu-id="9de3b-190">Converte o valor de data para o tempo equivalente em UTC.</span><span class="sxs-lookup"><span data-stu-id="9de3b-190">Converts the date value to the equivalent time in UTC.</span></span>

<span data-ttu-id="9de3b-191">Esse parâmetro foi introduzido no PowerShell 7,1.</span><span class="sxs-lookup"><span data-stu-id="9de3b-191">This parameter was introduced in PowerShell 7.1.</span></span>

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

### <span data-ttu-id="9de3b-192">-Data</span><span class="sxs-lookup"><span data-stu-id="9de3b-192">-Date</span></span>

<span data-ttu-id="9de3b-193">Especifica uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="9de3b-193">Specifies a date and time.</span></span> <span data-ttu-id="9de3b-194">O tempo é opcional e, se não for especificado, retornará 00:00:00.</span><span class="sxs-lookup"><span data-stu-id="9de3b-194">Time is optional and if not specified, returns 00:00:00.</span></span>

<span data-ttu-id="9de3b-195">Insira a data e a hora em um formato padrão para a localidade do sistema.</span><span class="sxs-lookup"><span data-stu-id="9de3b-195">Enter the date and time in a format that is standard for the system locale.</span></span>

<span data-ttu-id="9de3b-196">Por exemplo, em inglês americano:</span><span class="sxs-lookup"><span data-stu-id="9de3b-196">For example, in US English:</span></span>

<span data-ttu-id="9de3b-197">`Get-Date -Date "6/25/2019 12:30:22"` Retorna terça-feira, 25 de junho de 2019 12:30:22</span><span class="sxs-lookup"><span data-stu-id="9de3b-197">`Get-Date -Date "6/25/2019 12:30:22"` returns Tuesday, June 25, 2019 12:30:22</span></span>

```yaml
Type: System.DateTime
Parameter Sets: DateAndFormat, DateAndUFormat
Aliases: LastWriteTime

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9de3b-198">-Dia</span><span class="sxs-lookup"><span data-stu-id="9de3b-198">-Day</span></span>

<span data-ttu-id="9de3b-199">Especifica o dia do mês que é exibido.</span><span class="sxs-lookup"><span data-stu-id="9de3b-199">Specifies the day of the month that is displayed.</span></span> <span data-ttu-id="9de3b-200">Insira um valor de 1 a 31.</span><span class="sxs-lookup"><span data-stu-id="9de3b-200">Enter a value from 1 to 31.</span></span>

<span data-ttu-id="9de3b-201">Se o valor especificado for maior que o número de dias em um mês, o PowerShell adicionará o número de dias ao mês.</span><span class="sxs-lookup"><span data-stu-id="9de3b-201">If the specified value is greater than the number of days in a month, PowerShell adds the number of days to the month.</span></span> <span data-ttu-id="9de3b-202">Por exemplo, `Get-Date -Month 2 -Day 31` exibe **3 de março**, não **31 de fevereiro**.</span><span class="sxs-lookup"><span data-stu-id="9de3b-202">For example, `Get-Date -Month 2 -Day 31` displays **March 3**, not **February 31**.</span></span>

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

### <span data-ttu-id="9de3b-203">-DisplayHint</span><span class="sxs-lookup"><span data-stu-id="9de3b-203">-DisplayHint</span></span>

<span data-ttu-id="9de3b-204">Determina quais elementos de data e hora são exibidos.</span><span class="sxs-lookup"><span data-stu-id="9de3b-204">Determines which elements of the date and time are displayed.</span></span>

<span data-ttu-id="9de3b-205">Os valores aceitos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="9de3b-205">The accepted values are as follows:</span></span>

- <span data-ttu-id="9de3b-206">**Data**: exibe somente a data</span><span class="sxs-lookup"><span data-stu-id="9de3b-206">**Date**: displays only the date</span></span>
- <span data-ttu-id="9de3b-207">**Hora**: exibe apenas a hora</span><span class="sxs-lookup"><span data-stu-id="9de3b-207">**Time**: displays only the time</span></span>
- <span data-ttu-id="9de3b-208">**DateTime**: exibe a data e a hora</span><span class="sxs-lookup"><span data-stu-id="9de3b-208">**DateTime**: displays the date and time</span></span>

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

### <span data-ttu-id="9de3b-209">-Formato</span><span class="sxs-lookup"><span data-stu-id="9de3b-209">-Format</span></span>

<span data-ttu-id="9de3b-210">Exibe a data e hora no formato do Microsoft .NET Framework indicado pelo especificador de formato.</span><span class="sxs-lookup"><span data-stu-id="9de3b-210">Displays the date and time in the Microsoft .NET Framework format indicated by the format specifier.</span></span>
<span data-ttu-id="9de3b-211">O parâmetro **Format** gera um objeto **String** .</span><span class="sxs-lookup"><span data-stu-id="9de3b-211">The **Format** parameter outputs a **String** object.</span></span>

<span data-ttu-id="9de3b-212">Para obter uma lista de especificadores de formato .NET disponíveis, consulte [cadeias de caracteres de formato personalizado de data e hora](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span><span class="sxs-lookup"><span data-stu-id="9de3b-212">For a list of available .NET format specifiers, see [Custom date and time format strings](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span></span>

<span data-ttu-id="9de3b-213">Quando o parâmetro **Format** é usado, `Get-Date` obtém apenas as propriedades do objeto **DateTime** necessárias para exibir a data.</span><span class="sxs-lookup"><span data-stu-id="9de3b-213">When the **Format** parameter is used, `Get-Date` only gets the **DateTime** object's properties necessary to display the date.</span></span> <span data-ttu-id="9de3b-214">Como resultado, algumas das propriedades e métodos de objetos **DateTime** podem não estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="9de3b-214">As a result, some of the properties and methods of **DateTime** objects might not be available.</span></span>

<span data-ttu-id="9de3b-215">A partir do PowerShell 5,0, você pode usar os seguintes formatos adicionais como valores para o parâmetro de **formato** .</span><span class="sxs-lookup"><span data-stu-id="9de3b-215">Starting in PowerShell 5.0, you can use the following additional formats as values for the **Format** parameter.</span></span>

- <span data-ttu-id="9de3b-216">**Data de início**.</span><span class="sxs-lookup"><span data-stu-id="9de3b-216">**FileDate**.</span></span> <span data-ttu-id="9de3b-217">Uma representação amigável de arquivo ou caminho da data atual na hora local.</span><span class="sxs-lookup"><span data-stu-id="9de3b-217">A file or path-friendly representation of the current date in local time.</span></span> <span data-ttu-id="9de3b-218">O formato é `yyyyMMdd` (diferencia maiúsculas de minúsculas, usando um ano de 4 dígitos, um mês de 2 dígitos e um dia de 2 dígitos).</span><span class="sxs-lookup"><span data-stu-id="9de3b-218">The format is `yyyyMMdd` (case-sensitive, using a 4-digit year, 2-digit month, and 2-digit day).</span></span> <span data-ttu-id="9de3b-219">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9de3b-219">For example:</span></span>
  20190627.

- <span data-ttu-id="9de3b-220">**FileDateUniversal**.</span><span class="sxs-lookup"><span data-stu-id="9de3b-220">**FileDateUniversal**.</span></span> <span data-ttu-id="9de3b-221">Uma representação amigável de arquivo ou caminho da data atual em tempo universal (UTC).</span><span class="sxs-lookup"><span data-stu-id="9de3b-221">A file or path-friendly representation of the current date in universal time (UTC).</span></span> <span data-ttu-id="9de3b-222">O formato é `yyyyMMddZ` (diferencia maiúsculas de minúsculas, usando um ano de 4 dígitos, um mês de 2 dígitos, um dia de 2 dígitos e a letra `Z` como o indicador UTC).</span><span class="sxs-lookup"><span data-stu-id="9de3b-222">The format is `yyyyMMddZ` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, and the letter `Z` as the UTC indicator).</span></span> <span data-ttu-id="9de3b-223">Por exemplo: 20190627Z.</span><span class="sxs-lookup"><span data-stu-id="9de3b-223">For example: 20190627Z.</span></span>

- <span data-ttu-id="9de3b-224">**FileDateTime**.</span><span class="sxs-lookup"><span data-stu-id="9de3b-224">**FileDateTime**.</span></span> <span data-ttu-id="9de3b-225">Uma representação de arquivo ou de caminho amigável da data e hora atuais na hora local, no formato de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="9de3b-225">A file or path-friendly representation of the current date and time in local time, in 24-hour format.</span></span> <span data-ttu-id="9de3b-226">O formato é `yyyyMMddTHHmmssffff` (diferencia maiúsculas de minúsculas, usando um ano de 4 dígitos, um mês de 2 dígitos, um dia de 2 dígitos, a letra `T` como um separador de hora, hora de 2 dígitos, minuto de 2 dígitos, segundo de 2 dígitos e milissegundo de 4 dígitos).</span><span class="sxs-lookup"><span data-stu-id="9de3b-226">The format is `yyyyMMddTHHmmssffff` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, the letter `T` as a time separator, 2-digit hour, 2-digit minute, 2-digit second, and 4-digit millisecond).</span></span> <span data-ttu-id="9de3b-227">Por exemplo: 20190627T0840107271.</span><span class="sxs-lookup"><span data-stu-id="9de3b-227">For example: 20190627T0840107271.</span></span>

- <span data-ttu-id="9de3b-228">**FileDateTimeUniversal**.</span><span class="sxs-lookup"><span data-stu-id="9de3b-228">**FileDateTimeUniversal**.</span></span> <span data-ttu-id="9de3b-229">Uma representação amigável de arquivo ou caminho da data e hora atuais em UTC (hora universal), no formato de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="9de3b-229">A file or path-friendly representation of the current date and time in universal time (UTC), in 24-hour format.</span></span> <span data-ttu-id="9de3b-230">O formato é `yyyyMMddTHHmmssffffZ` (diferencia maiúsculas de minúsculas, usando um ano de 4 dígitos, um mês de 2 dígitos, um dia de 2 dígitos, a letra `T` como um separador de hora, hora de 2 dígitos, minuto de 2 dígitos, segundo de 2 dígitos, milissegundo de 4 dígitos e a letra `Z` como o indicador UTC).</span><span class="sxs-lookup"><span data-stu-id="9de3b-230">The format is `yyyyMMddTHHmmssffffZ` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, the letter `T` as a time separator, 2-digit hour, 2-digit minute, 2-digit second, 4-digit millisecond, and the letter `Z` as the UTC indicator).</span></span> <span data-ttu-id="9de3b-231">Por exemplo: 20190627T1540500718Z.</span><span class="sxs-lookup"><span data-stu-id="9de3b-231">For example: 20190627T1540500718Z.</span></span>

```yaml
Type: System.String
Parameter Sets: DateAndFormat, UnixTimeSecondsAndFormat
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9de3b-232">-Hora</span><span class="sxs-lookup"><span data-stu-id="9de3b-232">-Hour</span></span>

<span data-ttu-id="9de3b-233">Especifica a hora que é exibida.</span><span class="sxs-lookup"><span data-stu-id="9de3b-233">Specifies the hour that is displayed.</span></span> <span data-ttu-id="9de3b-234">Insira um valor de 0 a 23.</span><span class="sxs-lookup"><span data-stu-id="9de3b-234">Enter a value from 0 to 23.</span></span>

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

### <span data-ttu-id="9de3b-235">-Milissegundo</span><span class="sxs-lookup"><span data-stu-id="9de3b-235">-Millisecond</span></span>

<span data-ttu-id="9de3b-236">Especifica os milissegundos na data.</span><span class="sxs-lookup"><span data-stu-id="9de3b-236">Specifies the milliseconds in the date.</span></span> <span data-ttu-id="9de3b-237">Insira um valor de 0 a 999.</span><span class="sxs-lookup"><span data-stu-id="9de3b-237">Enter a value from 0 to 999.</span></span>

<span data-ttu-id="9de3b-238">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="9de3b-238">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="9de3b-239">-Minuto</span><span class="sxs-lookup"><span data-stu-id="9de3b-239">-Minute</span></span>

<span data-ttu-id="9de3b-240">Especifica o minuto que é exibido.</span><span class="sxs-lookup"><span data-stu-id="9de3b-240">Specifies the minute that is displayed.</span></span> <span data-ttu-id="9de3b-241">Insira um valor de 0 a 59.</span><span class="sxs-lookup"><span data-stu-id="9de3b-241">Enter a value from 0 to 59.</span></span>

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

### <span data-ttu-id="9de3b-242">-Mês</span><span class="sxs-lookup"><span data-stu-id="9de3b-242">-Month</span></span>

<span data-ttu-id="9de3b-243">Especifica o mês que é exibido.</span><span class="sxs-lookup"><span data-stu-id="9de3b-243">Specifies the month that is displayed.</span></span> <span data-ttu-id="9de3b-244">Insira um valor de 1 a 12.</span><span class="sxs-lookup"><span data-stu-id="9de3b-244">Enter a value from 1 to 12.</span></span>

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

### <span data-ttu-id="9de3b-245">-Segundo</span><span class="sxs-lookup"><span data-stu-id="9de3b-245">-Second</span></span>

<span data-ttu-id="9de3b-246">Especifica o segundo que é exibido.</span><span class="sxs-lookup"><span data-stu-id="9de3b-246">Specifies the second that is displayed.</span></span> <span data-ttu-id="9de3b-247">Insira um valor de 0 a 59.</span><span class="sxs-lookup"><span data-stu-id="9de3b-247">Enter a value from 0 to 59.</span></span>

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

### <span data-ttu-id="9de3b-248">-UFormat</span><span class="sxs-lookup"><span data-stu-id="9de3b-248">-UFormat</span></span>

<span data-ttu-id="9de3b-249">Exibe a data e hora no formato UNIX.</span><span class="sxs-lookup"><span data-stu-id="9de3b-249">Displays the date and time in UNIX format.</span></span> <span data-ttu-id="9de3b-250">O parâmetro **uFormat** gera um objeto de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9de3b-250">The **UFormat** parameter outputs a string object.</span></span>

<span data-ttu-id="9de3b-251">Os especificadores **uFormat** são precedidos por um sinal de porcentagem ( `%` ), por exemplo,, `%m` `%d` e `%Y` .</span><span class="sxs-lookup"><span data-stu-id="9de3b-251">**UFormat** specifiers are preceded by a percent sign (`%`), for example, `%m`, `%d`, and `%Y`.</span></span> <span data-ttu-id="9de3b-252">A seção [observações](#notes) contém uma tabela de **especificadores uFormat** válidos.</span><span class="sxs-lookup"><span data-stu-id="9de3b-252">The [Notes](#notes) section contains a table of valid **UFormat specifiers**.</span></span>

<span data-ttu-id="9de3b-253">Quando o parâmetro **uFormat** é usado, `Get-Date` obtém apenas as propriedades do objeto **DateTime** necessárias para exibir a data.</span><span class="sxs-lookup"><span data-stu-id="9de3b-253">When the **UFormat** parameter is used, `Get-Date` only gets the **DateTime** object's properties necessary to display the date.</span></span> <span data-ttu-id="9de3b-254">Como resultado, algumas das propriedades e métodos de objetos **DateTime** podem não estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="9de3b-254">As a result, some of the properties and methods of **DateTime** objects might not be available.</span></span>

```yaml
Type: System.String
Parameter Sets: DateAndUFormat, UnixTimeSecondsAndUFormat
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9de3b-255">-UnixTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="9de3b-255">-UnixTimeSeconds</span></span>

<span data-ttu-id="9de3b-256">Data e hora representadas em segundos desde 1º de janeiro de 1970, 0:00:00.</span><span class="sxs-lookup"><span data-stu-id="9de3b-256">Date and time represented in seconds since January 1, 1970, 0:00:00.</span></span>

<span data-ttu-id="9de3b-257">Esse parâmetro foi introduzido no PowerShell 7,1.</span><span class="sxs-lookup"><span data-stu-id="9de3b-257">This parameter was introduced in PowerShell 7.1.</span></span>

```yaml
Type: System.Int64
Parameter Sets: UnixTimeSecondsAndFormat, UnixTimeSecondsAndUFormat
Aliases: UnixTime

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9de3b-258">-Ano</span><span class="sxs-lookup"><span data-stu-id="9de3b-258">-Year</span></span>

<span data-ttu-id="9de3b-259">Especifica o ano que é exibido.</span><span class="sxs-lookup"><span data-stu-id="9de3b-259">Specifies the year that is displayed.</span></span> <span data-ttu-id="9de3b-260">Insira um valor de 1 a 9999.</span><span class="sxs-lookup"><span data-stu-id="9de3b-260">Enter a value from 1 to 9999.</span></span>

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

### <span data-ttu-id="9de3b-261">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9de3b-261">CommonParameters</span></span>

<span data-ttu-id="9de3b-262">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9de3b-262">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9de3b-263">Para obter mais informações, confira [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9de3b-263">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9de3b-264">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="9de3b-264">INPUTS</span></span>

### <span data-ttu-id="9de3b-265">Entrada de pipeline</span><span class="sxs-lookup"><span data-stu-id="9de3b-265">Pipeline input</span></span>

<span data-ttu-id="9de3b-266">`Get-Date` aceita a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="9de3b-266">`Get-Date` accepts pipeline input.</span></span> <span data-ttu-id="9de3b-267">Por exemplo, `Get-ChildItem | Get-Date`.</span><span class="sxs-lookup"><span data-stu-id="9de3b-267">For example, `Get-ChildItem | Get-Date`.</span></span>

## <span data-ttu-id="9de3b-268">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="9de3b-268">OUTPUTS</span></span>

### <span data-ttu-id="9de3b-269">System. DateTime ou System. String</span><span class="sxs-lookup"><span data-stu-id="9de3b-269">System.DateTime or System.String</span></span>

<span data-ttu-id="9de3b-270">`Get-Date` Retorna um objeto **DateTime** , exceto quando os parâmetros **Format** e **uFormat** são usados.</span><span class="sxs-lookup"><span data-stu-id="9de3b-270">`Get-Date` returns a **DateTime** object except when the **Format** and **UFormat** parameters are used.</span></span> <span data-ttu-id="9de3b-271">Os parâmetros **Format** ou **uFormat** retornam objetos de **cadeia de caracteres** .</span><span class="sxs-lookup"><span data-stu-id="9de3b-271">The **Format** or **UFormat** parameters return **String** objects.</span></span>

<span data-ttu-id="9de3b-272">Quando um objeto **DateTime** é enviado ao pipeline para um cmdlet como o `Add-Content` que espera entrada de cadeia de caracteres, o PowerShell converte o objeto em um objeto de cadeia de **caracteres** .</span><span class="sxs-lookup"><span data-stu-id="9de3b-272">When a **DateTime** object is sent down the pipeline to a cmdlet such as `Add-Content` that expects string input, PowerShell converts the object to a **String** object.</span></span>

<span data-ttu-id="9de3b-273">O método `(Get-Date).ToString()` converte um objeto **DateTime** em um objeto **String** .</span><span class="sxs-lookup"><span data-stu-id="9de3b-273">The method `(Get-Date).ToString()` converts a **DateTime** object a **String** object.</span></span>

<span data-ttu-id="9de3b-274">Para exibir as propriedades e os métodos de um objeto, envie o objeto para baixo no pipeline para `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="9de3b-274">To display an object's properties and methods, send the object down the pipeline to `Get-Member`.</span></span>
<span data-ttu-id="9de3b-275">Por exemplo, `Get-Date | Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="9de3b-275">For example, `Get-Date | Get-Member`.</span></span>

## <span data-ttu-id="9de3b-276">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="9de3b-276">NOTES</span></span>

<span data-ttu-id="9de3b-277">Os objetos **DateTime** estão em formatos de data e hora longa para a localidade do sistema.</span><span class="sxs-lookup"><span data-stu-id="9de3b-277">**DateTime** objects are in long-date and long-time formats for the system locale.</span></span>

<span data-ttu-id="9de3b-278">Os **especificadores uFormat** válidos são exibidos na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="9de3b-278">The valid **UFormat specifiers** are displayed in the following table:</span></span>

| <span data-ttu-id="9de3b-279">Especificador de formato</span><span class="sxs-lookup"><span data-stu-id="9de3b-279">Format specifier</span></span> |                                 <span data-ttu-id="9de3b-280">Significado</span><span class="sxs-lookup"><span data-stu-id="9de3b-280">Meaning</span></span>                     |         <span data-ttu-id="9de3b-281">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9de3b-281">Example</span></span>          |
| ---- | ----------------------------------------------------------------------- | ------------------------ |
| `%A` | <span data-ttu-id="9de3b-282">Dia da semana-nome completo</span><span class="sxs-lookup"><span data-stu-id="9de3b-282">Day of the week - full name</span></span>                                             | <span data-ttu-id="9de3b-283">Monday</span><span class="sxs-lookup"><span data-stu-id="9de3b-283">Monday</span></span>                   |
| `%a` | <span data-ttu-id="9de3b-284">Dia da semana-nome abreviado</span><span class="sxs-lookup"><span data-stu-id="9de3b-284">Day of the week - abbreviated name</span></span>                                      | <span data-ttu-id="9de3b-285">Mon</span><span class="sxs-lookup"><span data-stu-id="9de3b-285">Mon</span></span>                      |
| `%B` | <span data-ttu-id="9de3b-286">Nome do mês-completo</span><span class="sxs-lookup"><span data-stu-id="9de3b-286">Month name - full</span></span>                                                       | <span data-ttu-id="9de3b-287">Janeiro</span><span class="sxs-lookup"><span data-stu-id="9de3b-287">January</span></span>                  |
| `%b` | <span data-ttu-id="9de3b-288">Nome do mês-abreviado</span><span class="sxs-lookup"><span data-stu-id="9de3b-288">Month name - abbreviated</span></span>                                                | <span data-ttu-id="9de3b-289">Jan</span><span class="sxs-lookup"><span data-stu-id="9de3b-289">Jan</span></span>                      |
| `%C` | <span data-ttu-id="9de3b-290">Anos</span><span class="sxs-lookup"><span data-stu-id="9de3b-290">Century</span></span>                                                                 | <span data-ttu-id="9de3b-291">20 para 2019</span><span class="sxs-lookup"><span data-stu-id="9de3b-291">20 for 2019</span></span>              |
| `%c` | <span data-ttu-id="9de3b-292">Data e hora abreviadas</span><span class="sxs-lookup"><span data-stu-id="9de3b-292">Date and time - abbreviated</span></span>                                             | <span data-ttu-id="9de3b-293">Quinta-feira-Jun 27 08:44:18 2019</span><span class="sxs-lookup"><span data-stu-id="9de3b-293">Thu Jun 27 08:44:18 2019</span></span> |
| `%D` | <span data-ttu-id="9de3b-294">Data no formato mm/dd/aa</span><span class="sxs-lookup"><span data-stu-id="9de3b-294">Date in mm/dd/yy format</span></span>                                                 | <span data-ttu-id="9de3b-295">06/27/19</span><span class="sxs-lookup"><span data-stu-id="9de3b-295">06/27/19</span></span>                 |
| `%d` | <span data-ttu-id="9de3b-296">Dia do mês-2 dígitos</span><span class="sxs-lookup"><span data-stu-id="9de3b-296">Day of the month - 2 digits</span></span>                                             | <span data-ttu-id="9de3b-297">05</span><span class="sxs-lookup"><span data-stu-id="9de3b-297">05</span></span>                       |
| `%e` | <span data-ttu-id="9de3b-298">Dia do mês-precedido por um espaço se houver apenas um único dígito</span><span class="sxs-lookup"><span data-stu-id="9de3b-298">Day of the month - preceded by a space if only a single digit</span></span>           | <span data-ttu-id="9de3b-299">\<space\>05</span><span class="sxs-lookup"><span data-stu-id="9de3b-299">\<space\>5</span></span>               |
| `%F` | <span data-ttu-id="9de3b-300">Data no formato aaaa-mm-dd, igual a% Y-% m-% d (o formato de data ISO 8601)</span><span class="sxs-lookup"><span data-stu-id="9de3b-300">Date in YYYY-mm-dd format, equal to %Y-%m-%d (the ISO 8601 date format)</span></span> | <span data-ttu-id="9de3b-301">2019-06-27</span><span class="sxs-lookup"><span data-stu-id="9de3b-301">2019-06-27</span></span>               |
| `%G` | <span data-ttu-id="9de3b-302">O mesmo que ' Y '</span><span class="sxs-lookup"><span data-stu-id="9de3b-302">Same as 'Y'</span></span>                                                             |                          |
| `%g` | <span data-ttu-id="9de3b-303">O mesmo que ' y '</span><span class="sxs-lookup"><span data-stu-id="9de3b-303">Same as 'y'</span></span>                                                             |                          |
| `%H` | <span data-ttu-id="9de3b-304">Hora no formato de 24 horas</span><span class="sxs-lookup"><span data-stu-id="9de3b-304">Hour in 24-hour format</span></span>                                                  | <span data-ttu-id="9de3b-305">17</span><span class="sxs-lookup"><span data-stu-id="9de3b-305">17</span></span>                       |
| `%h` | <span data-ttu-id="9de3b-306">Mesmo que ' b '</span><span class="sxs-lookup"><span data-stu-id="9de3b-306">Same as 'b'</span></span>                                                             |                          |
| `%I` | <span data-ttu-id="9de3b-307">Hora no formato de 12 horas</span><span class="sxs-lookup"><span data-stu-id="9de3b-307">Hour in 12-hour format</span></span>                                                  | <span data-ttu-id="9de3b-308">05</span><span class="sxs-lookup"><span data-stu-id="9de3b-308">05</span></span>                       |
| `%j` | <span data-ttu-id="9de3b-309">Dia do ano</span><span class="sxs-lookup"><span data-stu-id="9de3b-309">Day of the year</span></span>                                                         | <span data-ttu-id="9de3b-310">1-366</span><span class="sxs-lookup"><span data-stu-id="9de3b-310">1-366</span></span>                    |
| `%k` | <span data-ttu-id="9de3b-311">Mesmo que ' H '</span><span class="sxs-lookup"><span data-stu-id="9de3b-311">Same as 'H'</span></span>                                                             |                          |
| `%l` | <span data-ttu-id="9de3b-312">O mesmo que ' I ' (I maiúsculo)</span><span class="sxs-lookup"><span data-stu-id="9de3b-312">Same as 'I' (Upper-case I)</span></span>                                              | <span data-ttu-id="9de3b-313">05</span><span class="sxs-lookup"><span data-stu-id="9de3b-313">05</span></span>                       |
| `%M` | <span data-ttu-id="9de3b-314">minutos</span><span class="sxs-lookup"><span data-stu-id="9de3b-314">Minutes</span></span>                                                                 | <span data-ttu-id="9de3b-315">35</span><span class="sxs-lookup"><span data-stu-id="9de3b-315">35</span></span>                       |
| `%m` | <span data-ttu-id="9de3b-316">Número do mês</span><span class="sxs-lookup"><span data-stu-id="9de3b-316">Month number</span></span>                                                            | <span data-ttu-id="9de3b-317">06</span><span class="sxs-lookup"><span data-stu-id="9de3b-317">06</span></span>                       |
| `%n` | <span data-ttu-id="9de3b-318">caractere de nova linha</span><span class="sxs-lookup"><span data-stu-id="9de3b-318">newline character</span></span>                                                       |                          |
| `%p` | <span data-ttu-id="9de3b-319">AM ou PM</span><span class="sxs-lookup"><span data-stu-id="9de3b-319">AM or PM</span></span>                                                                |                          |
| `%R` | <span data-ttu-id="9de3b-320">Tempo no formato de 24 horas-sem segundos</span><span class="sxs-lookup"><span data-stu-id="9de3b-320">Time in 24-hour format -no seconds</span></span>                                      | <span data-ttu-id="9de3b-321">17:45</span><span class="sxs-lookup"><span data-stu-id="9de3b-321">17:45</span></span>                    |
| `%r` | <span data-ttu-id="9de3b-322">Hora no formato de 12 horas</span><span class="sxs-lookup"><span data-stu-id="9de3b-322">Time in 12-hour format</span></span>                                                  | <span data-ttu-id="9de3b-323">09:15:36 AM</span><span class="sxs-lookup"><span data-stu-id="9de3b-323">09:15:36 AM</span></span>              |
| `%S` | <span data-ttu-id="9de3b-324">Segundos</span><span class="sxs-lookup"><span data-stu-id="9de3b-324">Seconds</span></span>                                                                 | <span data-ttu-id="9de3b-325">05</span><span class="sxs-lookup"><span data-stu-id="9de3b-325">05</span></span>                       |
| `%s` | <span data-ttu-id="9de3b-326">Segundos decorridos desde 1º de janeiro de 1970 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9de3b-326">Seconds elapsed since January 1, 1970 00:00:00</span></span>                          | <span data-ttu-id="9de3b-327">1150451174</span><span class="sxs-lookup"><span data-stu-id="9de3b-327">1150451174</span></span>               |
| `%t` | <span data-ttu-id="9de3b-328">Caractere de tabulação horizontal</span><span class="sxs-lookup"><span data-stu-id="9de3b-328">Horizontal tab character</span></span>                                                |                          |
| `%T` | <span data-ttu-id="9de3b-329">Tempo no formato de 24 horas</span><span class="sxs-lookup"><span data-stu-id="9de3b-329">Time in 24-hour format</span></span>                                                  | <span data-ttu-id="9de3b-330">17:45:52</span><span class="sxs-lookup"><span data-stu-id="9de3b-330">17:45:52</span></span>                 |
| `%U` | <span data-ttu-id="9de3b-331">Mesmo que ' W '</span><span class="sxs-lookup"><span data-stu-id="9de3b-331">Same as 'W'</span></span>                                                             |                          |
| `%u` | <span data-ttu-id="9de3b-332">Dia numérico da semana (1-7)</span><span class="sxs-lookup"><span data-stu-id="9de3b-332">Numeric day of the week (1-7)</span></span>                                           | <span data-ttu-id="9de3b-333">Segunda-feira = 1, domingo = 7</span><span class="sxs-lookup"><span data-stu-id="9de3b-333">Monday = 1, Sunday = 7</span></span>   |
| `%V` | <span data-ttu-id="9de3b-334">Semana do ano</span><span class="sxs-lookup"><span data-stu-id="9de3b-334">Week of the year</span></span>                                                        | <span data-ttu-id="9de3b-335">01-53</span><span class="sxs-lookup"><span data-stu-id="9de3b-335">01-53</span></span>                    |
| `%w` | <span data-ttu-id="9de3b-336">Dia numérico da semana (0-6)</span><span class="sxs-lookup"><span data-stu-id="9de3b-336">Numeric day of the week (0-6)</span></span>                                           | <span data-ttu-id="9de3b-337">Domingo = 0, sábado = 6</span><span class="sxs-lookup"><span data-stu-id="9de3b-337">Sunday = 0, Saturday = 6</span></span> |
| `%W` | <span data-ttu-id="9de3b-338">Semana do ano</span><span class="sxs-lookup"><span data-stu-id="9de3b-338">Week of the year</span></span>                                                        | <span data-ttu-id="9de3b-339">00-52</span><span class="sxs-lookup"><span data-stu-id="9de3b-339">00-52</span></span>                    |
| `%X` | <span data-ttu-id="9de3b-340">Igual a ' T'</span><span class="sxs-lookup"><span data-stu-id="9de3b-340">Same as 'T'</span></span>                                                             |                          |
| `%x` | <span data-ttu-id="9de3b-341">Data no formato padrão para localidade</span><span class="sxs-lookup"><span data-stu-id="9de3b-341">Date in standard format for locale</span></span>                                      | <span data-ttu-id="9de3b-342">06/27/19 para inglês-EUA</span><span class="sxs-lookup"><span data-stu-id="9de3b-342">06/27/19 for English-US</span></span>  |
| `%Y` | <span data-ttu-id="9de3b-343">Ano no formato de 4 dígitos</span><span class="sxs-lookup"><span data-stu-id="9de3b-343">Year in 4-digit format</span></span>                                                  | <span data-ttu-id="9de3b-344">2019</span><span class="sxs-lookup"><span data-stu-id="9de3b-344">2019</span></span>                     |
| `%y` | <span data-ttu-id="9de3b-345">Ano no formato de 2 dígitos</span><span class="sxs-lookup"><span data-stu-id="9de3b-345">Year in 2-digit format</span></span>                                                  | <span data-ttu-id="9de3b-346">19</span><span class="sxs-lookup"><span data-stu-id="9de3b-346">19</span></span>                       |
| `%Z` | <span data-ttu-id="9de3b-347">Deslocamento de fuso horário da coordenada de tempo universal (UTC)</span><span class="sxs-lookup"><span data-stu-id="9de3b-347">Time zone offset from Universal Time Coordinate (UTC)</span></span>                   | <span data-ttu-id="9de3b-348">-07</span><span class="sxs-lookup"><span data-stu-id="9de3b-348">-07</span></span>                      |

## <span data-ttu-id="9de3b-349">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="9de3b-349">RELATED LINKS</span></span>

[<span data-ttu-id="9de3b-350">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="9de3b-350">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="9de3b-351">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="9de3b-351">Get-Culture</span></span>](Get-Culture.md)

[<span data-ttu-id="9de3b-352">Get-Member</span><span class="sxs-lookup"><span data-stu-id="9de3b-352">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="9de3b-353">New-Item</span><span class="sxs-lookup"><span data-stu-id="9de3b-353">New-Item</span></span>](../Microsoft.PowerShell.Management/New-Item.md)

[<span data-ttu-id="9de3b-354">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="9de3b-354">New-TimeSpan</span></span>](New-TimeSpan.md)

[<span data-ttu-id="9de3b-355">Set-Date</span><span class="sxs-lookup"><span data-stu-id="9de3b-355">Set-Date</span></span>](Set-Date.md)
