---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Date
ms.openlocfilehash: 34b0d7833d858a8b71c28d0f872ddb9e4948b76d
ms.sourcegitcommit: 077488408c820c860131382324bdd576d0edf52a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95514976"
---
# <span data-ttu-id="234aa-103">Get-Date</span><span class="sxs-lookup"><span data-stu-id="234aa-103">Get-Date</span></span>

## <span data-ttu-id="234aa-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="234aa-104">SYNOPSIS</span></span>
<span data-ttu-id="234aa-105">Obtém a data e hora atuais.</span><span class="sxs-lookup"><span data-stu-id="234aa-105">Gets the current date and time.</span></span>

## <span data-ttu-id="234aa-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="234aa-106">SYNTAX</span></span>

### <span data-ttu-id="234aa-107">Data (padrão)</span><span class="sxs-lookup"><span data-stu-id="234aa-107">Date (Default)</span></span>

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-Format <String>] [-AsUTC] [<CommonParameters>]
```

### <span data-ttu-id="234aa-108">DateUFormat</span><span class="sxs-lookup"><span data-stu-id="234aa-108">DateUFormat</span></span>

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 -UFormat <String> [<CommonParameters>]
```

### <span data-ttu-id="234aa-109">UnixTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="234aa-109">UnixTimeSeconds</span></span>

```
Get-Date -UnixTimeSeconds <Int64> [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-Format <String>] [-AsUTC] [<CommonParameters>]
```

### <span data-ttu-id="234aa-110">UnixTimeSecondsUFormat</span><span class="sxs-lookup"><span data-stu-id="234aa-110">UnixTimeSecondsUFormat</span></span>

```
Get-Date -UnixTimeSeconds <Int64> [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 -UFormat <String> [<CommonParameters>]
```

## <span data-ttu-id="234aa-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="234aa-111">DESCRIPTION</span></span>

<span data-ttu-id="234aa-112">O `Get-Date` cmdlet obtém um objeto **DateTime** que representa a data atual ou uma data que você especifica.</span><span class="sxs-lookup"><span data-stu-id="234aa-112">The `Get-Date` cmdlet gets a **DateTime** object that represents the current date or a date that you specify.</span></span> <span data-ttu-id="234aa-113">`Get-Date` pode formatar a data e a hora em vários formatos .NET e UNIX.</span><span class="sxs-lookup"><span data-stu-id="234aa-113">`Get-Date` can format the date and time in several .NET and UNIX formats.</span></span> <span data-ttu-id="234aa-114">Você pode usar `Get-Date` para gerar uma cadeia de caracteres de caractere de data ou hora e, em seguida, enviar a cadeia de caracteres para outros cmdlets ou programas.</span><span class="sxs-lookup"><span data-stu-id="234aa-114">You can use `Get-Date` to generate a date or time character string, and then send the string to other cmdlets or programs.</span></span>

<span data-ttu-id="234aa-115">`Get-Date` usa as configurações de cultura do computador para determinar como a saída é formatada.</span><span class="sxs-lookup"><span data-stu-id="234aa-115">`Get-Date` uses the computer's culture settings to determine how the output is formatted.</span></span> <span data-ttu-id="234aa-116">Para exibir as configurações do computador, use `(Get-Culture).DateTimeFormat` .</span><span class="sxs-lookup"><span data-stu-id="234aa-116">To view your computer's settings, use `(Get-Culture).DateTimeFormat`.</span></span>

## <span data-ttu-id="234aa-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="234aa-117">EXAMPLES</span></span>

### <span data-ttu-id="234aa-118">Exemplo 1: obter a data e a hora atuais</span><span class="sxs-lookup"><span data-stu-id="234aa-118">Example 1: Get the current date and time</span></span>

<span data-ttu-id="234aa-119">Neste exemplo, `Get-Date` exibe a data e hora atuais do sistema.</span><span class="sxs-lookup"><span data-stu-id="234aa-119">In this example, `Get-Date` displays the current system date and time.</span></span> <span data-ttu-id="234aa-120">A saída está nos formatos de longa data e de hora longa.</span><span class="sxs-lookup"><span data-stu-id="234aa-120">The output is in the long-date and long-time formats.</span></span>

```powershell
Get-Date
```

```Output
Tuesday, June 25, 2019 14:53:32
```

### <span data-ttu-id="234aa-121">Exemplo 2: obter elementos da data e hora atuais</span><span class="sxs-lookup"><span data-stu-id="234aa-121">Example 2: Get elements of the current date and time</span></span>

<span data-ttu-id="234aa-122">Este exemplo mostra como usar `Get-Date` para obter o elemento Date ou time.</span><span class="sxs-lookup"><span data-stu-id="234aa-122">This example shows how to use `Get-Date` to get either the date or time element.</span></span> <span data-ttu-id="234aa-123">O parâmetro usa os argumentos **Date**, **time** ou **DateTime**.</span><span class="sxs-lookup"><span data-stu-id="234aa-123">The parameter uses the arguments **Date**, **Time**, or **DateTime**.</span></span>

```powershell
Get-Date -DisplayHint Date
```

```Output
Tuesday, June 25, 2019
```

<span data-ttu-id="234aa-124">`Get-Date` usa o parâmetro **DisplayHint** com o argumento **Date** para obter apenas a data.</span><span class="sxs-lookup"><span data-stu-id="234aa-124">`Get-Date` uses the **DisplayHint** parameter with the **Date** argument to get only the date.</span></span>

### <span data-ttu-id="234aa-125">Exemplo 3: obter a data e a hora com um especificador de formato .NET</span><span class="sxs-lookup"><span data-stu-id="234aa-125">Example 3: Get the date and time with a .NET format specifier</span></span>

<span data-ttu-id="234aa-126">Neste exemplo, um especificador de formato .NET é usado para personalizar o formato da saída.</span><span class="sxs-lookup"><span data-stu-id="234aa-126">In this example, a .NET format specifier is used to customize the output's format.</span></span> <span data-ttu-id="234aa-127">A saída é um objeto de **cadeia de caracteres** .</span><span class="sxs-lookup"><span data-stu-id="234aa-127">The output is a **String** object.</span></span>

```powershell
Get-Date -Format "dddd MM/dd/yyyy HH:mm K"
```

```Output
Tuesday 06/25/2019 16:17 -07:00
```

<span data-ttu-id="234aa-128">`Get-Date` usa o parâmetro **Format** para especificar vários especificadores de formato.</span><span class="sxs-lookup"><span data-stu-id="234aa-128">`Get-Date` uses the **Format** parameter to specify several format specifiers.</span></span>

<span data-ttu-id="234aa-129">Os especificadores de formato .NET usados neste exemplo são definidos da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="234aa-129">The .NET format specifiers used in this example are defined as follows:</span></span>

| <span data-ttu-id="234aa-130">Especificador</span><span class="sxs-lookup"><span data-stu-id="234aa-130">Specifier</span></span> |                      <span data-ttu-id="234aa-131">Definição</span><span class="sxs-lookup"><span data-stu-id="234aa-131">Definition</span></span>                       |
| --------- | ----------------------------------------------------- |
| `dddd`    | <span data-ttu-id="234aa-132">Dia da semana-nome completo</span><span class="sxs-lookup"><span data-stu-id="234aa-132">Day of the week - full name</span></span>                           |
| `MM`      | <span data-ttu-id="234aa-133">Número do mês</span><span class="sxs-lookup"><span data-stu-id="234aa-133">Month number</span></span>                                          |
| `dd`      | <span data-ttu-id="234aa-134">Dia do mês-2 dígitos</span><span class="sxs-lookup"><span data-stu-id="234aa-134">Day of the month - 2 digits</span></span>                           |
| `yyyy`    | <span data-ttu-id="234aa-135">Ano no formato de 4 dígitos</span><span class="sxs-lookup"><span data-stu-id="234aa-135">Year in 4-digit format</span></span>                                |
| `HH:mm`   | <span data-ttu-id="234aa-136">Tempo no formato de 24 horas-sem segundos</span><span class="sxs-lookup"><span data-stu-id="234aa-136">Time in 24-hour format - no seconds</span></span>                    |
| `K`       | <span data-ttu-id="234aa-137">Deslocamento de fuso horário da coordenada de tempo universal (UTC)</span><span class="sxs-lookup"><span data-stu-id="234aa-137">Time zone offset from Universal Time Coordinate (UTC)</span></span> |

<span data-ttu-id="234aa-138">Para obter mais informações sobre especificadores de formato .NET, consulte [cadeias de caracteres de formato personalizado de data e hora](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span><span class="sxs-lookup"><span data-stu-id="234aa-138">For more information about .NET format specifiers, see [Custom date and time format strings](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span></span>

### <span data-ttu-id="234aa-139">Exemplo 4: obter a data e a hora com um especificador UFormat</span><span class="sxs-lookup"><span data-stu-id="234aa-139">Example 4: Get the date and time with a UFormat specifier</span></span>

<span data-ttu-id="234aa-140">Neste exemplo, vários especificadores de formato **uFormat** são usados para personalizar o formato da saída.</span><span class="sxs-lookup"><span data-stu-id="234aa-140">In this example, several **UFormat** format specifiers are used to customize the output's format.</span></span>
<span data-ttu-id="234aa-141">A saída é um objeto de **cadeia de caracteres** .</span><span class="sxs-lookup"><span data-stu-id="234aa-141">The output is a **String** object.</span></span>

```powershell
Get-Date -UFormat "%A %m/%d/%Y %R %Z"
```

```Output
Tuesday 06/25/2019 16:19 -07
```

<span data-ttu-id="234aa-142">`Get-Date` usa o parâmetro **uFormat** para especificar vários especificadores de formato.</span><span class="sxs-lookup"><span data-stu-id="234aa-142">`Get-Date` uses the **UFormat** parameter to specify several format specifiers.</span></span>

<span data-ttu-id="234aa-143">Os especificadores de formato **uFormat** usados neste exemplo são definidos da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="234aa-143">The **UFormat** format specifiers used in this example are defined as follows:</span></span>

| <span data-ttu-id="234aa-144">Especificador</span><span class="sxs-lookup"><span data-stu-id="234aa-144">Specifier</span></span> |                      <span data-ttu-id="234aa-145">Definição</span><span class="sxs-lookup"><span data-stu-id="234aa-145">Definition</span></span>                       |
| --------- | ----------------------------------------------------- |
| `%A`      | <span data-ttu-id="234aa-146">Dia da semana-nome completo</span><span class="sxs-lookup"><span data-stu-id="234aa-146">Day of the week - full name</span></span>                           |
| `%m`      | <span data-ttu-id="234aa-147">Número do mês</span><span class="sxs-lookup"><span data-stu-id="234aa-147">Month number</span></span>                                          |
| `%d`      | <span data-ttu-id="234aa-148">Dia do mês-2 dígitos</span><span class="sxs-lookup"><span data-stu-id="234aa-148">Day of the month - 2 digits</span></span>                           |
| `%Y`      | <span data-ttu-id="234aa-149">Ano no formato de 4 dígitos</span><span class="sxs-lookup"><span data-stu-id="234aa-149">Year in 4-digit format</span></span>                                |
| `%R`      | <span data-ttu-id="234aa-150">Tempo no formato de 24 horas-sem segundos</span><span class="sxs-lookup"><span data-stu-id="234aa-150">Time in 24-hour format - no seconds</span></span>                    |
| `%Z`      | <span data-ttu-id="234aa-151">Deslocamento de fuso horário da coordenada de tempo universal (UTC)</span><span class="sxs-lookup"><span data-stu-id="234aa-151">Time zone offset from Universal Time Coordinate (UTC)</span></span> |

<span data-ttu-id="234aa-152">Para obter uma lista de especificadores de formato **uFormat** válidos, consulte a seção [observações](#notes) .</span><span class="sxs-lookup"><span data-stu-id="234aa-152">For a list of valid **UFormat** format specifiers, see the [Notes](#notes) section.</span></span>

### <span data-ttu-id="234aa-153">Exemplo 5: obter o dia do ano de uma data</span><span class="sxs-lookup"><span data-stu-id="234aa-153">Example 5: Get a date's day of the year</span></span>

<span data-ttu-id="234aa-154">Neste exemplo, uma propriedade é usada para obter o dia numérico do ano.</span><span class="sxs-lookup"><span data-stu-id="234aa-154">In this example, a property is used to get the numeric day of the year.</span></span>

<span data-ttu-id="234aa-155">O calendário gregoriano tem 365 dias, exceto os anos bissextos que têm 366 dias.</span><span class="sxs-lookup"><span data-stu-id="234aa-155">The Gregorian calendar has 365 days, except for leap years that have 366 days.</span></span> <span data-ttu-id="234aa-156">Por exemplo, 31 de dezembro de 2020 é o dia 366.</span><span class="sxs-lookup"><span data-stu-id="234aa-156">For example, December 31, 2020 is day 366.</span></span>

```powershell
(Get-Date -Year 2020 -Month 12 -Day 31).DayOfYear
```

```Output
366
```

<span data-ttu-id="234aa-157">`Get-Date` usa três parâmetros para especificar a data: **ano**, **mês** e **dia**.</span><span class="sxs-lookup"><span data-stu-id="234aa-157">`Get-Date` uses three parameters to specify the date: **Year**, **Month**, and **Day**.</span></span> <span data-ttu-id="234aa-158">O comando é encapsulado com parênteses para que o resultado seja avaliado pela propriedade **DayofYear** .</span><span class="sxs-lookup"><span data-stu-id="234aa-158">The command is wrapped with parentheses so that the result is evaluated by the **DayofYear** property.</span></span>

### <span data-ttu-id="234aa-159">Exemplo 6: verificar se uma data está ajustada para o horário de verão</span><span class="sxs-lookup"><span data-stu-id="234aa-159">Example 6: Check if a date is adjusted for daylight savings time</span></span>

<span data-ttu-id="234aa-160">Este exemplo usa um método booliano para verificar se uma data é ajustada pelo horário de verão.</span><span class="sxs-lookup"><span data-stu-id="234aa-160">This example uses a boolean method to verify if a date is adjusted by daylight savings time.</span></span>

```powershell
$DST = Get-Date
$DST.IsDaylightSavingTime()
```

```Output
True
```

<span data-ttu-id="234aa-161">Uma variável, `$DST` armazena o resultado de `Get-Date` .</span><span class="sxs-lookup"><span data-stu-id="234aa-161">A variable, `$DST` stores the result of `Get-Date`.</span></span> <span data-ttu-id="234aa-162">`$DST` usa o método **IsDaylightSavingTime** para testar se a data é ajustada para o horário de verão.</span><span class="sxs-lookup"><span data-stu-id="234aa-162">`$DST` uses the **IsDaylightSavingTime** method to test if the date is adjusted for daylight savings time.</span></span>

### <span data-ttu-id="234aa-163">Exemplo 7: converter a hora atual em hora UTC</span><span class="sxs-lookup"><span data-stu-id="234aa-163">Example 7: Convert the current time to UTC time</span></span>

<span data-ttu-id="234aa-164">Neste exemplo, a hora atual é convertida em hora UTC.</span><span class="sxs-lookup"><span data-stu-id="234aa-164">In this example, the current time is converted to UTC time.</span></span> <span data-ttu-id="234aa-165">O deslocamento UTC para a localidade do sistema é usado para converter a hora.</span><span class="sxs-lookup"><span data-stu-id="234aa-165">The UTC offset for the system's locale is used to convert the time.</span></span> <span data-ttu-id="234aa-166">Uma tabela na seção [observações](#notes) lista os especificadores de formato **uFormat** válidos.</span><span class="sxs-lookup"><span data-stu-id="234aa-166">A table in the [Notes](#notes) section lists the valid **UFormat** format specifiers.</span></span>

```powershell
Get-Date -UFormat "%A %B/%d/%Y %T %Z"
$Time = Get-Date
$Time.ToUniversalTime()
```

```Output
Wednesday June/26/2019 10:45:26 -07

Wednesday, June 26, 2019 17:45:26
```

<span data-ttu-id="234aa-167">`Get-Date` usa o parâmetro **uFormat** com especificadores de formato para exibir a data e a hora atuais do sistema.</span><span class="sxs-lookup"><span data-stu-id="234aa-167">`Get-Date` uses the **UFormat** parameter with format specifiers to display the current system date and time.</span></span> <span data-ttu-id="234aa-168">O especificador de formato **% Z** representa o deslocamento UTC de **-07**.</span><span class="sxs-lookup"><span data-stu-id="234aa-168">The format specifier **%Z** represents the UTC offset of **-07**.</span></span>

<span data-ttu-id="234aa-169">A `$Time` variável armazena a data e a hora atuais do sistema.</span><span class="sxs-lookup"><span data-stu-id="234aa-169">The `$Time` variable stores the current system date and time.</span></span> <span data-ttu-id="234aa-170">`$Time` usa o método **ToUniversalTime ()** para converter a hora com base no deslocamento UTC do computador.</span><span class="sxs-lookup"><span data-stu-id="234aa-170">`$Time` uses the **ToUniversalTime()** method to convert the time based on the computer's UTC offset.</span></span>

### <span data-ttu-id="234aa-171">Exemplo 8: criar um carimbo de data/hora</span><span class="sxs-lookup"><span data-stu-id="234aa-171">Example 8: Create a timestamp</span></span>

<span data-ttu-id="234aa-172">Neste exemplo, um especificador de formato cria um objeto de **cadeia de caracteres** de carimbo de data/hora para um nome de diretório.</span><span class="sxs-lookup"><span data-stu-id="234aa-172">In this example, a format specifier creates a timestamp **String** object for a directory name.</span></span> <span data-ttu-id="234aa-173">O timestamp inclui a data, a hora e o deslocamento UTC.</span><span class="sxs-lookup"><span data-stu-id="234aa-173">The timestamp includes the date, time, and UTC offset.</span></span>

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

<span data-ttu-id="234aa-174">A `$timestamp` variável armazena os resultados de um `Get-Date` comando.</span><span class="sxs-lookup"><span data-stu-id="234aa-174">The `$timestamp` variable stores the results of a `Get-Date` command.</span></span> <span data-ttu-id="234aa-175">`Get-Date` usa o parâmetro **Format** com o especificador de formato de minúsculas `o` para criar um objeto de **cadeia de caracteres** de carimbo de data/hora.</span><span class="sxs-lookup"><span data-stu-id="234aa-175">`Get-Date` uses the **Format** parameter with the format specifier of lowercase `o` to create a timestamp **String** object.</span></span> <span data-ttu-id="234aa-176">O objeto é enviado ao pipeline para `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="234aa-176">The object is sent down the pipeline to `ForEach-Object`.</span></span> <span data-ttu-id="234aa-177">Um **scriptblock** contém a `$_` variável que representa o objeto de pipeline atual.</span><span class="sxs-lookup"><span data-stu-id="234aa-177">A **ScriptBlock** contains the `$_` variable that represents the current pipeline object.</span></span> <span data-ttu-id="234aa-178">A cadeia de caracteres de carimbo de data/hora é delimitada por dois-pontos que são substituídos por pontos.</span><span class="sxs-lookup"><span data-stu-id="234aa-178">The timestamp string is delimited by colons that are replaced by periods.</span></span>

<span data-ttu-id="234aa-179">`New-Item` usa o parâmetro **path** para especificar o local de um novo diretório.</span><span class="sxs-lookup"><span data-stu-id="234aa-179">`New-Item` uses the **Path** parameter to specify the location for a new directory.</span></span> <span data-ttu-id="234aa-180">O caminho inclui a `$timestamp` variável como o nome do diretório.</span><span class="sxs-lookup"><span data-stu-id="234aa-180">The path includes the `$timestamp` variable as the directory name.</span></span> <span data-ttu-id="234aa-181">O parâmetro de **tipo** especifica que um diretório é criado.</span><span class="sxs-lookup"><span data-stu-id="234aa-181">The **Type** parameter specifies that a directory is created.</span></span>

### <span data-ttu-id="234aa-182">Exemplo 9: converter um carimbo de data/hora UNIX</span><span class="sxs-lookup"><span data-stu-id="234aa-182">Example 9: Convert a Unix timestamp</span></span>

<span data-ttu-id="234aa-183">Este exemplo converte um tempo do UNIX (representado pelo número de segundos desde 1970-01-01 0:00:00) em DateTime.</span><span class="sxs-lookup"><span data-stu-id="234aa-183">This example converts a Unix time (represented by the number of seconds since 1970-01-01 0:00:00) to DateTime.</span></span>

```powershell
Get-Date -UnixTimeSeconds 1577836800
```

```Output
Wednesday, January 01, 2020 12:00:00 AM
```

### <span data-ttu-id="234aa-184">Exemplo 10: retornar um valor de data interpretado como UTC</span><span class="sxs-lookup"><span data-stu-id="234aa-184">Example 10: Return a date value interpreted as UTC</span></span>

<span data-ttu-id="234aa-185">Este exemplo mostra como interpretar um valor de data como seu equivalente UTC.</span><span class="sxs-lookup"><span data-stu-id="234aa-185">This example shows how to interpret a date value as its UTC equivalent.</span></span> <span data-ttu-id="234aa-186">Para o exemplo, essa máquina é definida como **hora padrão do Pacífico**.</span><span class="sxs-lookup"><span data-stu-id="234aa-186">For the example, this machine is set to **Pacific Standard Time**.</span></span> <span data-ttu-id="234aa-187">Por padrão, `Get-Date` retorna valores para esse fuso horário.</span><span class="sxs-lookup"><span data-stu-id="234aa-187">By default, `Get-Date` returns values for that timezone.</span></span> <span data-ttu-id="234aa-188">Use o parâmetro **AsUTC** para converter o valor para a hora equivalente UTC.</span><span class="sxs-lookup"><span data-stu-id="234aa-188">Use the **AsUTC** parameter to convert the value to the UTC equivalent time.</span></span>

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

## <span data-ttu-id="234aa-189">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="234aa-189">PARAMETERS</span></span>

### <span data-ttu-id="234aa-190">-AsUTC</span><span class="sxs-lookup"><span data-stu-id="234aa-190">-AsUTC</span></span>

<span data-ttu-id="234aa-191">Converte o valor de data para o tempo equivalente em UTC.</span><span class="sxs-lookup"><span data-stu-id="234aa-191">Converts the date value to the equivalent time in UTC.</span></span>

<span data-ttu-id="234aa-192">Esse parâmetro foi introduzido no PowerShell 7,1.</span><span class="sxs-lookup"><span data-stu-id="234aa-192">This parameter was introduced in PowerShell 7.1.</span></span>

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

### <span data-ttu-id="234aa-193">-Data</span><span class="sxs-lookup"><span data-stu-id="234aa-193">-Date</span></span>

<span data-ttu-id="234aa-194">Especifica uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="234aa-194">Specifies a date and time.</span></span> <span data-ttu-id="234aa-195">O tempo é opcional e, se não for especificado, retornará 00:00:00.</span><span class="sxs-lookup"><span data-stu-id="234aa-195">Time is optional and if not specified, returns 00:00:00.</span></span>

<span data-ttu-id="234aa-196">Insira a data e a hora em um formato padrão para a localidade do sistema.</span><span class="sxs-lookup"><span data-stu-id="234aa-196">Enter the date and time in a format that is standard for the system locale.</span></span>

<span data-ttu-id="234aa-197">Por exemplo, em inglês americano:</span><span class="sxs-lookup"><span data-stu-id="234aa-197">For example, in US English:</span></span>

<span data-ttu-id="234aa-198">`Get-Date -Date "6/25/2019 12:30:22"` Retorna terça-feira, 25 de junho de 2019 12:30:22</span><span class="sxs-lookup"><span data-stu-id="234aa-198">`Get-Date -Date "6/25/2019 12:30:22"` returns Tuesday, June 25, 2019 12:30:22</span></span>

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

### <span data-ttu-id="234aa-199">-Dia</span><span class="sxs-lookup"><span data-stu-id="234aa-199">-Day</span></span>

<span data-ttu-id="234aa-200">Especifica o dia do mês que é exibido.</span><span class="sxs-lookup"><span data-stu-id="234aa-200">Specifies the day of the month that is displayed.</span></span> <span data-ttu-id="234aa-201">Insira um valor de 1 a 31.</span><span class="sxs-lookup"><span data-stu-id="234aa-201">Enter a value from 1 to 31.</span></span>

<span data-ttu-id="234aa-202">Se o valor especificado for maior que o número de dias em um mês, o PowerShell adicionará o número de dias ao mês.</span><span class="sxs-lookup"><span data-stu-id="234aa-202">If the specified value is greater than the number of days in a month, PowerShell adds the number of days to the month.</span></span> <span data-ttu-id="234aa-203">Por exemplo, `Get-Date -Month 2 -Day 31` exibe **3 de março**, não **31 de fevereiro**.</span><span class="sxs-lookup"><span data-stu-id="234aa-203">For example, `Get-Date -Month 2 -Day 31` displays **March 3**, not **February 31**.</span></span>

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

### <span data-ttu-id="234aa-204">-DisplayHint</span><span class="sxs-lookup"><span data-stu-id="234aa-204">-DisplayHint</span></span>

<span data-ttu-id="234aa-205">Determina quais elementos de data e hora são exibidos.</span><span class="sxs-lookup"><span data-stu-id="234aa-205">Determines which elements of the date and time are displayed.</span></span>

<span data-ttu-id="234aa-206">Os valores aceitos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="234aa-206">The accepted values are as follows:</span></span>

- <span data-ttu-id="234aa-207">**Data**: exibe somente a data</span><span class="sxs-lookup"><span data-stu-id="234aa-207">**Date**: displays only the date</span></span>
- <span data-ttu-id="234aa-208">**Hora**: exibe apenas a hora</span><span class="sxs-lookup"><span data-stu-id="234aa-208">**Time**: displays only the time</span></span>
- <span data-ttu-id="234aa-209">**DateTime**: exibe a data e a hora</span><span class="sxs-lookup"><span data-stu-id="234aa-209">**DateTime**: displays the date and time</span></span>

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

### <span data-ttu-id="234aa-210">-Formato</span><span class="sxs-lookup"><span data-stu-id="234aa-210">-Format</span></span>

<span data-ttu-id="234aa-211">Exibe a data e hora no formato do Microsoft .NET Framework indicado pelo especificador de formato.</span><span class="sxs-lookup"><span data-stu-id="234aa-211">Displays the date and time in the Microsoft .NET Framework format indicated by the format specifier.</span></span>
<span data-ttu-id="234aa-212">O parâmetro **Format** gera um objeto **String** .</span><span class="sxs-lookup"><span data-stu-id="234aa-212">The **Format** parameter outputs a **String** object.</span></span>

<span data-ttu-id="234aa-213">Para obter uma lista de especificadores de formato .NET disponíveis, consulte [cadeias de caracteres de formato personalizado de data e hora](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span><span class="sxs-lookup"><span data-stu-id="234aa-213">For a list of available .NET format specifiers, see [Custom date and time format strings](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span></span>

<span data-ttu-id="234aa-214">Quando o parâmetro **Format** é usado, `Get-Date` obtém apenas as propriedades do objeto **DateTime** necessárias para exibir a data.</span><span class="sxs-lookup"><span data-stu-id="234aa-214">When the **Format** parameter is used, `Get-Date` only gets the **DateTime** object's properties necessary to display the date.</span></span> <span data-ttu-id="234aa-215">Como resultado, algumas das propriedades e métodos de objetos **DateTime** podem não estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="234aa-215">As a result, some of the properties and methods of **DateTime** objects might not be available.</span></span>

<span data-ttu-id="234aa-216">A partir do PowerShell 5,0, você pode usar os seguintes formatos adicionais como valores para o parâmetro de **formato** .</span><span class="sxs-lookup"><span data-stu-id="234aa-216">Starting in PowerShell 5.0, you can use the following additional formats as values for the **Format** parameter.</span></span>

- <span data-ttu-id="234aa-217">**Data de início**.</span><span class="sxs-lookup"><span data-stu-id="234aa-217">**FileDate**.</span></span> <span data-ttu-id="234aa-218">Uma representação amigável de arquivo ou caminho da data atual na hora local.</span><span class="sxs-lookup"><span data-stu-id="234aa-218">A file or path-friendly representation of the current date in local time.</span></span> <span data-ttu-id="234aa-219">O formato é `yyyyMMdd` (diferencia maiúsculas de minúsculas, usando um ano de 4 dígitos, um mês de 2 dígitos e um dia de 2 dígitos).</span><span class="sxs-lookup"><span data-stu-id="234aa-219">The format is `yyyyMMdd` (case-sensitive, using a 4-digit year, 2-digit month, and 2-digit day).</span></span> <span data-ttu-id="234aa-220">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="234aa-220">For example:</span></span>
  20190627.

- <span data-ttu-id="234aa-221">**FileDateUniversal**.</span><span class="sxs-lookup"><span data-stu-id="234aa-221">**FileDateUniversal**.</span></span> <span data-ttu-id="234aa-222">Uma representação amigável de arquivo ou caminho da data atual em tempo universal (UTC).</span><span class="sxs-lookup"><span data-stu-id="234aa-222">A file or path-friendly representation of the current date in universal time (UTC).</span></span> <span data-ttu-id="234aa-223">O formato é `yyyyMMddZ` (diferencia maiúsculas de minúsculas, usando um ano de 4 dígitos, um mês de 2 dígitos, um dia de 2 dígitos e a letra `Z` como o indicador UTC).</span><span class="sxs-lookup"><span data-stu-id="234aa-223">The format is `yyyyMMddZ` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, and the letter `Z` as the UTC indicator).</span></span> <span data-ttu-id="234aa-224">Por exemplo: 20190627Z.</span><span class="sxs-lookup"><span data-stu-id="234aa-224">For example: 20190627Z.</span></span>

- <span data-ttu-id="234aa-225">**FileDateTime**.</span><span class="sxs-lookup"><span data-stu-id="234aa-225">**FileDateTime**.</span></span> <span data-ttu-id="234aa-226">Uma representação de arquivo ou de caminho amigável da data e hora atuais na hora local, no formato de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="234aa-226">A file or path-friendly representation of the current date and time in local time, in 24-hour format.</span></span> <span data-ttu-id="234aa-227">O formato é `yyyyMMddTHHmmssffff` (diferencia maiúsculas de minúsculas, usando um ano de 4 dígitos, um mês de 2 dígitos, um dia de 2 dígitos, a letra `T` como um separador de hora, hora de 2 dígitos, minuto de 2 dígitos, segundo de 2 dígitos e milissegundo de 4 dígitos).</span><span class="sxs-lookup"><span data-stu-id="234aa-227">The format is `yyyyMMddTHHmmssffff` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, the letter `T` as a time separator, 2-digit hour, 2-digit minute, 2-digit second, and 4-digit millisecond).</span></span> <span data-ttu-id="234aa-228">Por exemplo: 20190627T0840107271.</span><span class="sxs-lookup"><span data-stu-id="234aa-228">For example: 20190627T0840107271.</span></span>

- <span data-ttu-id="234aa-229">**FileDateTimeUniversal**.</span><span class="sxs-lookup"><span data-stu-id="234aa-229">**FileDateTimeUniversal**.</span></span> <span data-ttu-id="234aa-230">Uma representação amigável de arquivo ou caminho da data e hora atuais em UTC (hora universal), no formato de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="234aa-230">A file or path-friendly representation of the current date and time in universal time (UTC), in 24-hour format.</span></span> <span data-ttu-id="234aa-231">O formato é `yyyyMMddTHHmmssffffZ` (diferencia maiúsculas de minúsculas, usando um ano de 4 dígitos, um mês de 2 dígitos, um dia de 2 dígitos, a letra `T` como um separador de hora, hora de 2 dígitos, minuto de 2 dígitos, segundo de 2 dígitos, milissegundo de 4 dígitos e a letra `Z` como o indicador UTC).</span><span class="sxs-lookup"><span data-stu-id="234aa-231">The format is `yyyyMMddTHHmmssffffZ` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, the letter `T` as a time separator, 2-digit hour, 2-digit minute, 2-digit second, 4-digit millisecond, and the letter `Z` as the UTC indicator).</span></span> <span data-ttu-id="234aa-232">Por exemplo: 20190627T1540500718Z.</span><span class="sxs-lookup"><span data-stu-id="234aa-232">For example: 20190627T1540500718Z.</span></span>

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

### <span data-ttu-id="234aa-233">-Hora</span><span class="sxs-lookup"><span data-stu-id="234aa-233">-Hour</span></span>

<span data-ttu-id="234aa-234">Especifica a hora que é exibida.</span><span class="sxs-lookup"><span data-stu-id="234aa-234">Specifies the hour that is displayed.</span></span> <span data-ttu-id="234aa-235">Insira um valor de 0 a 23.</span><span class="sxs-lookup"><span data-stu-id="234aa-235">Enter a value from 0 to 23.</span></span>

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

### <span data-ttu-id="234aa-236">-Milissegundo</span><span class="sxs-lookup"><span data-stu-id="234aa-236">-Millisecond</span></span>

<span data-ttu-id="234aa-237">Especifica os milissegundos na data.</span><span class="sxs-lookup"><span data-stu-id="234aa-237">Specifies the milliseconds in the date.</span></span> <span data-ttu-id="234aa-238">Insira um valor de 0 a 999.</span><span class="sxs-lookup"><span data-stu-id="234aa-238">Enter a value from 0 to 999.</span></span>

<span data-ttu-id="234aa-239">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="234aa-239">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="234aa-240">-Minuto</span><span class="sxs-lookup"><span data-stu-id="234aa-240">-Minute</span></span>

<span data-ttu-id="234aa-241">Especifica o minuto que é exibido.</span><span class="sxs-lookup"><span data-stu-id="234aa-241">Specifies the minute that is displayed.</span></span> <span data-ttu-id="234aa-242">Insira um valor de 0 a 59.</span><span class="sxs-lookup"><span data-stu-id="234aa-242">Enter a value from 0 to 59.</span></span>

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

### <span data-ttu-id="234aa-243">-Mês</span><span class="sxs-lookup"><span data-stu-id="234aa-243">-Month</span></span>

<span data-ttu-id="234aa-244">Especifica o mês que é exibido.</span><span class="sxs-lookup"><span data-stu-id="234aa-244">Specifies the month that is displayed.</span></span> <span data-ttu-id="234aa-245">Insira um valor de 1 a 12.</span><span class="sxs-lookup"><span data-stu-id="234aa-245">Enter a value from 1 to 12.</span></span>

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

### <span data-ttu-id="234aa-246">-Segundo</span><span class="sxs-lookup"><span data-stu-id="234aa-246">-Second</span></span>

<span data-ttu-id="234aa-247">Especifica o segundo que é exibido.</span><span class="sxs-lookup"><span data-stu-id="234aa-247">Specifies the second that is displayed.</span></span> <span data-ttu-id="234aa-248">Insira um valor de 0 a 59.</span><span class="sxs-lookup"><span data-stu-id="234aa-248">Enter a value from 0 to 59.</span></span>

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

### <span data-ttu-id="234aa-249">-UFormat</span><span class="sxs-lookup"><span data-stu-id="234aa-249">-UFormat</span></span>

<span data-ttu-id="234aa-250">Exibe a data e hora no formato UNIX.</span><span class="sxs-lookup"><span data-stu-id="234aa-250">Displays the date and time in UNIX format.</span></span> <span data-ttu-id="234aa-251">O parâmetro **uFormat** gera um objeto de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="234aa-251">The **UFormat** parameter outputs a string object.</span></span>

<span data-ttu-id="234aa-252">Os especificadores **uFormat** são precedidos por um sinal de porcentagem ( `%` ), por exemplo,, `%m` `%d` e `%Y` .</span><span class="sxs-lookup"><span data-stu-id="234aa-252">**UFormat** specifiers are preceded by a percent sign (`%`), for example, `%m`, `%d`, and `%Y`.</span></span> <span data-ttu-id="234aa-253">A seção [observações](#notes) contém uma tabela de **especificadores uFormat** válidos.</span><span class="sxs-lookup"><span data-stu-id="234aa-253">The [Notes](#notes) section contains a table of valid **UFormat specifiers**.</span></span>

<span data-ttu-id="234aa-254">Quando o parâmetro **uFormat** é usado, `Get-Date` obtém apenas as propriedades do objeto **DateTime** necessárias para exibir a data.</span><span class="sxs-lookup"><span data-stu-id="234aa-254">When the **UFormat** parameter is used, `Get-Date` only gets the **DateTime** object's properties necessary to display the date.</span></span> <span data-ttu-id="234aa-255">Como resultado, algumas das propriedades e métodos de objetos **DateTime** podem não estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="234aa-255">As a result, some of the properties and methods of **DateTime** objects might not be available.</span></span>

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

### <span data-ttu-id="234aa-256">-UnixTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="234aa-256">-UnixTimeSeconds</span></span>

<span data-ttu-id="234aa-257">Data e hora representadas em segundos desde 1º de janeiro de 1970, 0:00:00.</span><span class="sxs-lookup"><span data-stu-id="234aa-257">Date and time represented in seconds since January 1, 1970, 0:00:00.</span></span>

<span data-ttu-id="234aa-258">Esse parâmetro foi introduzido no PowerShell 7,1.</span><span class="sxs-lookup"><span data-stu-id="234aa-258">This parameter was introduced in PowerShell 7.1.</span></span>

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

### <span data-ttu-id="234aa-259">-Ano</span><span class="sxs-lookup"><span data-stu-id="234aa-259">-Year</span></span>

<span data-ttu-id="234aa-260">Especifica o ano que é exibido.</span><span class="sxs-lookup"><span data-stu-id="234aa-260">Specifies the year that is displayed.</span></span> <span data-ttu-id="234aa-261">Insira um valor de 1 a 9999.</span><span class="sxs-lookup"><span data-stu-id="234aa-261">Enter a value from 1 to 9999.</span></span>

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

### <span data-ttu-id="234aa-262">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="234aa-262">CommonParameters</span></span>

<span data-ttu-id="234aa-263">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="234aa-263">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="234aa-264">Para obter mais informações, confira [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="234aa-264">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="234aa-265">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="234aa-265">INPUTS</span></span>

### <span data-ttu-id="234aa-266">Entrada de pipeline</span><span class="sxs-lookup"><span data-stu-id="234aa-266">Pipeline input</span></span>

<span data-ttu-id="234aa-267">`Get-Date` aceita a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="234aa-267">`Get-Date` accepts pipeline input.</span></span> <span data-ttu-id="234aa-268">Por exemplo, `Get-ChildItem | Get-Date`.</span><span class="sxs-lookup"><span data-stu-id="234aa-268">For example, `Get-ChildItem | Get-Date`.</span></span>

## <span data-ttu-id="234aa-269">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="234aa-269">OUTPUTS</span></span>

### <span data-ttu-id="234aa-270">System. DateTime ou System. String</span><span class="sxs-lookup"><span data-stu-id="234aa-270">System.DateTime or System.String</span></span>

<span data-ttu-id="234aa-271">`Get-Date` Retorna um objeto **DateTime** , exceto quando os parâmetros **Format** e **uFormat** são usados.</span><span class="sxs-lookup"><span data-stu-id="234aa-271">`Get-Date` returns a **DateTime** object except when the **Format** and **UFormat** parameters are used.</span></span> <span data-ttu-id="234aa-272">Os parâmetros **Format** ou **uFormat** retornam objetos de **cadeia de caracteres** .</span><span class="sxs-lookup"><span data-stu-id="234aa-272">The **Format** or **UFormat** parameters return **String** objects.</span></span>

<span data-ttu-id="234aa-273">Quando um objeto **DateTime** é enviado ao pipeline para um cmdlet como o `Add-Content` que espera entrada de cadeia de caracteres, o PowerShell converte o objeto em um objeto de cadeia de **caracteres** .</span><span class="sxs-lookup"><span data-stu-id="234aa-273">When a **DateTime** object is sent down the pipeline to a cmdlet such as `Add-Content` that expects string input, PowerShell converts the object to a **String** object.</span></span>

<span data-ttu-id="234aa-274">O método `(Get-Date).ToString()` converte um objeto **DateTime** em um objeto **String** .</span><span class="sxs-lookup"><span data-stu-id="234aa-274">The method `(Get-Date).ToString()` converts a **DateTime** object a **String** object.</span></span>

<span data-ttu-id="234aa-275">Para exibir as propriedades e os métodos de um objeto, envie o objeto para baixo no pipeline para `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="234aa-275">To display an object's properties and methods, send the object down the pipeline to `Get-Member`.</span></span>
<span data-ttu-id="234aa-276">Por exemplo, `Get-Date | Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="234aa-276">For example, `Get-Date | Get-Member`.</span></span>

## <span data-ttu-id="234aa-277">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="234aa-277">NOTES</span></span>

<span data-ttu-id="234aa-278">Os objetos **DateTime** estão em formatos de data e hora longa para a localidade do sistema.</span><span class="sxs-lookup"><span data-stu-id="234aa-278">**DateTime** objects are in long-date and long-time formats for the system locale.</span></span>

<span data-ttu-id="234aa-279">Os **especificadores uFormat** válidos são exibidos na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="234aa-279">The valid **UFormat specifiers** are displayed in the following table:</span></span>

| <span data-ttu-id="234aa-280">Especificador de formato</span><span class="sxs-lookup"><span data-stu-id="234aa-280">Format specifier</span></span> |                                 <span data-ttu-id="234aa-281">Significado</span><span class="sxs-lookup"><span data-stu-id="234aa-281">Meaning</span></span>                     |         <span data-ttu-id="234aa-282">Exemplo</span><span class="sxs-lookup"><span data-stu-id="234aa-282">Example</span></span>          |
| ---- | ----------------------------------------------------------------------- | ------------------------ |
| `%A` | <span data-ttu-id="234aa-283">Dia da semana-nome completo</span><span class="sxs-lookup"><span data-stu-id="234aa-283">Day of the week - full name</span></span>                                             | <span data-ttu-id="234aa-284">Monday</span><span class="sxs-lookup"><span data-stu-id="234aa-284">Monday</span></span>                   |
| `%a` | <span data-ttu-id="234aa-285">Dia da semana-nome abreviado</span><span class="sxs-lookup"><span data-stu-id="234aa-285">Day of the week - abbreviated name</span></span>                                      | <span data-ttu-id="234aa-286">Mon</span><span class="sxs-lookup"><span data-stu-id="234aa-286">Mon</span></span>                      |
| `%B` | <span data-ttu-id="234aa-287">Nome do mês-completo</span><span class="sxs-lookup"><span data-stu-id="234aa-287">Month name - full</span></span>                                                       | <span data-ttu-id="234aa-288">Janeiro</span><span class="sxs-lookup"><span data-stu-id="234aa-288">January</span></span>                  |
| `%b` | <span data-ttu-id="234aa-289">Nome do mês-abreviado</span><span class="sxs-lookup"><span data-stu-id="234aa-289">Month name - abbreviated</span></span>                                                | <span data-ttu-id="234aa-290">Jan</span><span class="sxs-lookup"><span data-stu-id="234aa-290">Jan</span></span>                      |
| `%C` | <span data-ttu-id="234aa-291">Anos</span><span class="sxs-lookup"><span data-stu-id="234aa-291">Century</span></span>                                                                 | <span data-ttu-id="234aa-292">20 para 2019</span><span class="sxs-lookup"><span data-stu-id="234aa-292">20 for 2019</span></span>              |
| `%c` | <span data-ttu-id="234aa-293">Data e hora abreviadas</span><span class="sxs-lookup"><span data-stu-id="234aa-293">Date and time - abbreviated</span></span>                                             | <span data-ttu-id="234aa-294">Quinta-feira-Jun 27 08:44:18 2019</span><span class="sxs-lookup"><span data-stu-id="234aa-294">Thu Jun 27 08:44:18 2019</span></span> |
| `%D` | <span data-ttu-id="234aa-295">Data no formato mm/dd/aa</span><span class="sxs-lookup"><span data-stu-id="234aa-295">Date in mm/dd/yy format</span></span>                                                 | <span data-ttu-id="234aa-296">06/27/19</span><span class="sxs-lookup"><span data-stu-id="234aa-296">06/27/19</span></span>                 |
| `%d` | <span data-ttu-id="234aa-297">Dia do mês-2 dígitos</span><span class="sxs-lookup"><span data-stu-id="234aa-297">Day of the month - 2 digits</span></span>                                             | <span data-ttu-id="234aa-298">05</span><span class="sxs-lookup"><span data-stu-id="234aa-298">05</span></span>                       |
| `%e` | <span data-ttu-id="234aa-299">Dia do mês-precedido por um espaço se houver apenas um único dígito</span><span class="sxs-lookup"><span data-stu-id="234aa-299">Day of the month - preceded by a space if only a single digit</span></span>           | <span data-ttu-id="234aa-300">\<space\>05</span><span class="sxs-lookup"><span data-stu-id="234aa-300">\<space\>5</span></span>               |
| `%F` | <span data-ttu-id="234aa-301">Data no formato aaaa-mm-dd, igual a% Y-% m-% d (o formato de data ISO 8601)</span><span class="sxs-lookup"><span data-stu-id="234aa-301">Date in YYYY-mm-dd format, equal to %Y-%m-%d (the ISO 8601 date format)</span></span> | <span data-ttu-id="234aa-302">2019-06-27</span><span class="sxs-lookup"><span data-stu-id="234aa-302">2019-06-27</span></span>               |
| `%G` | <span data-ttu-id="234aa-303">O mesmo que ' Y '</span><span class="sxs-lookup"><span data-stu-id="234aa-303">Same as 'Y'</span></span>                                                             |                          |
| `%g` | <span data-ttu-id="234aa-304">O mesmo que ' y '</span><span class="sxs-lookup"><span data-stu-id="234aa-304">Same as 'y'</span></span>                                                             |                          |
| `%H` | <span data-ttu-id="234aa-305">Hora no formato de 24 horas</span><span class="sxs-lookup"><span data-stu-id="234aa-305">Hour in 24-hour format</span></span>                                                  | <span data-ttu-id="234aa-306">17</span><span class="sxs-lookup"><span data-stu-id="234aa-306">17</span></span>                       |
| `%h` | <span data-ttu-id="234aa-307">Mesmo que ' b '</span><span class="sxs-lookup"><span data-stu-id="234aa-307">Same as 'b'</span></span>                                                             |                          |
| `%I` | <span data-ttu-id="234aa-308">Hora no formato de 12 horas</span><span class="sxs-lookup"><span data-stu-id="234aa-308">Hour in 12-hour format</span></span>                                                  | <span data-ttu-id="234aa-309">05</span><span class="sxs-lookup"><span data-stu-id="234aa-309">05</span></span>                       |
| `%j` | <span data-ttu-id="234aa-310">Dia do ano</span><span class="sxs-lookup"><span data-stu-id="234aa-310">Day of the year</span></span>                                                         | <span data-ttu-id="234aa-311">1-366</span><span class="sxs-lookup"><span data-stu-id="234aa-311">1-366</span></span>                    |
| `%k` | <span data-ttu-id="234aa-312">Mesmo que ' H '</span><span class="sxs-lookup"><span data-stu-id="234aa-312">Same as 'H'</span></span>                                                             |                          |
| `%l` | <span data-ttu-id="234aa-313">O mesmo que ' I ' (I maiúsculo)</span><span class="sxs-lookup"><span data-stu-id="234aa-313">Same as 'I' (Upper-case I)</span></span>                                              | <span data-ttu-id="234aa-314">05</span><span class="sxs-lookup"><span data-stu-id="234aa-314">05</span></span>                       |
| `%M` | <span data-ttu-id="234aa-315">minutos</span><span class="sxs-lookup"><span data-stu-id="234aa-315">Minutes</span></span>                                                                 | <span data-ttu-id="234aa-316">35</span><span class="sxs-lookup"><span data-stu-id="234aa-316">35</span></span>                       |
| `%m` | <span data-ttu-id="234aa-317">Número do mês</span><span class="sxs-lookup"><span data-stu-id="234aa-317">Month number</span></span>                                                            | <span data-ttu-id="234aa-318">06</span><span class="sxs-lookup"><span data-stu-id="234aa-318">06</span></span>                       |
| `%n` | <span data-ttu-id="234aa-319">caractere de nova linha</span><span class="sxs-lookup"><span data-stu-id="234aa-319">newline character</span></span>                                                       |                          |
| `%p` | <span data-ttu-id="234aa-320">AM ou PM</span><span class="sxs-lookup"><span data-stu-id="234aa-320">AM or PM</span></span>                                                                |                          |
| `%R` | <span data-ttu-id="234aa-321">Tempo no formato de 24 horas-sem segundos</span><span class="sxs-lookup"><span data-stu-id="234aa-321">Time in 24-hour format -no seconds</span></span>                                      | <span data-ttu-id="234aa-322">17:45</span><span class="sxs-lookup"><span data-stu-id="234aa-322">17:45</span></span>                    |
| `%r` | <span data-ttu-id="234aa-323">Hora no formato de 12 horas</span><span class="sxs-lookup"><span data-stu-id="234aa-323">Time in 12-hour format</span></span>                                                  | <span data-ttu-id="234aa-324">09:15:36 AM</span><span class="sxs-lookup"><span data-stu-id="234aa-324">09:15:36 AM</span></span>              |
| `%S` | <span data-ttu-id="234aa-325">Segundos</span><span class="sxs-lookup"><span data-stu-id="234aa-325">Seconds</span></span>                                                                 | <span data-ttu-id="234aa-326">05</span><span class="sxs-lookup"><span data-stu-id="234aa-326">05</span></span>                       |
| `%s` | <span data-ttu-id="234aa-327">Segundos decorridos desde 1º de janeiro de 1970 00:00:00</span><span class="sxs-lookup"><span data-stu-id="234aa-327">Seconds elapsed since January 1, 1970 00:00:00</span></span>                          | <span data-ttu-id="234aa-328">1150451174</span><span class="sxs-lookup"><span data-stu-id="234aa-328">1150451174</span></span>               |
| `%t` | <span data-ttu-id="234aa-329">Caractere de tabulação horizontal</span><span class="sxs-lookup"><span data-stu-id="234aa-329">Horizontal tab character</span></span>                                                |                          |
| `%T` | <span data-ttu-id="234aa-330">Tempo no formato de 24 horas</span><span class="sxs-lookup"><span data-stu-id="234aa-330">Time in 24-hour format</span></span>                                                  | <span data-ttu-id="234aa-331">17:45:52</span><span class="sxs-lookup"><span data-stu-id="234aa-331">17:45:52</span></span>                 |
| `%U` | <span data-ttu-id="234aa-332">Mesmo que ' W '</span><span class="sxs-lookup"><span data-stu-id="234aa-332">Same as 'W'</span></span>                                                             |                          |
| `%u` | <span data-ttu-id="234aa-333">Dia da semana-número</span><span class="sxs-lookup"><span data-stu-id="234aa-333">Day of the week - number</span></span>                                                | <span data-ttu-id="234aa-334">Domingo = 0</span><span class="sxs-lookup"><span data-stu-id="234aa-334">Sunday = 0</span></span>               |
| `%V` | <span data-ttu-id="234aa-335">Semana do ano</span><span class="sxs-lookup"><span data-stu-id="234aa-335">Week of the year</span></span>                                                        | <span data-ttu-id="234aa-336">01-53</span><span class="sxs-lookup"><span data-stu-id="234aa-336">01-53</span></span>                    |
| `%w` | <span data-ttu-id="234aa-337">Mesmo que ' u '</span><span class="sxs-lookup"><span data-stu-id="234aa-337">Same as 'u'</span></span>                                                             |                          |
| `%W` | <span data-ttu-id="234aa-338">Semana do ano</span><span class="sxs-lookup"><span data-stu-id="234aa-338">Week of the year</span></span>                                                        | <span data-ttu-id="234aa-339">00-52</span><span class="sxs-lookup"><span data-stu-id="234aa-339">00-52</span></span>                    |
| `%X` | <span data-ttu-id="234aa-340">Igual a ' T'</span><span class="sxs-lookup"><span data-stu-id="234aa-340">Same as 'T'</span></span>                                                             |                          |
| `%x` | <span data-ttu-id="234aa-341">Data no formato padrão para localidade</span><span class="sxs-lookup"><span data-stu-id="234aa-341">Date in standard format for locale</span></span>                                      | <span data-ttu-id="234aa-342">06/27/19 para inglês-EUA</span><span class="sxs-lookup"><span data-stu-id="234aa-342">06/27/19 for English-US</span></span>  |
| `%Y` | <span data-ttu-id="234aa-343">Ano no formato de 4 dígitos</span><span class="sxs-lookup"><span data-stu-id="234aa-343">Year in 4-digit format</span></span>                                                  | <span data-ttu-id="234aa-344">2019</span><span class="sxs-lookup"><span data-stu-id="234aa-344">2019</span></span>                     |
| `%y` | <span data-ttu-id="234aa-345">Ano no formato de 2 dígitos</span><span class="sxs-lookup"><span data-stu-id="234aa-345">Year in 2-digit format</span></span>                                                  | <span data-ttu-id="234aa-346">19</span><span class="sxs-lookup"><span data-stu-id="234aa-346">19</span></span>                       |
| `%Z` | <span data-ttu-id="234aa-347">Deslocamento de fuso horário da coordenada de tempo universal (UTC)</span><span class="sxs-lookup"><span data-stu-id="234aa-347">Time zone offset from Universal Time Coordinate (UTC)</span></span>                   | <span data-ttu-id="234aa-348">-07</span><span class="sxs-lookup"><span data-stu-id="234aa-348">-07</span></span>                      |

## <span data-ttu-id="234aa-349">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="234aa-349">RELATED LINKS</span></span>

[<span data-ttu-id="234aa-350">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="234aa-350">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="234aa-351">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="234aa-351">Get-Culture</span></span>](Get-Culture.md)

[<span data-ttu-id="234aa-352">Get-Member</span><span class="sxs-lookup"><span data-stu-id="234aa-352">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="234aa-353">New-Item</span><span class="sxs-lookup"><span data-stu-id="234aa-353">New-Item</span></span>](../Microsoft.PowerShell.Management/New-Item.md)

[<span data-ttu-id="234aa-354">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="234aa-354">New-TimeSpan</span></span>](New-TimeSpan.md)

[<span data-ttu-id="234aa-355">Set-Date</span><span class="sxs-lookup"><span data-stu-id="234aa-355">Set-Date</span></span>](Set-Date.md)
