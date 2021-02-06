---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/01/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-timespan?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-TimeSpan
ms.openlocfilehash: 5808685a5560d1cbf91c6705b90643c35702b28a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596592"
---
# <span data-ttu-id="95d2c-102">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="95d2c-102">New-TimeSpan</span></span>

## <span data-ttu-id="95d2c-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="95d2c-103">SYNOPSIS</span></span>
<span data-ttu-id="95d2c-104">Cria um objeto TimeSpan.</span><span class="sxs-lookup"><span data-stu-id="95d2c-104">Creates a TimeSpan object.</span></span>

## <span data-ttu-id="95d2c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="95d2c-105">SYNTAX</span></span>

### <span data-ttu-id="95d2c-106">Data (padrão)</span><span class="sxs-lookup"><span data-stu-id="95d2c-106">Date (Default)</span></span>

```
New-TimeSpan [[-Start] <DateTime>] [[-End] <DateTime>] [<CommonParameters>]
```

### <span data-ttu-id="95d2c-107">Hora</span><span class="sxs-lookup"><span data-stu-id="95d2c-107">Time</span></span>

```
New-TimeSpan [-Days <Int32>] [-Hours <Int32>] [-Minutes <Int32>] [-Seconds <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="95d2c-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="95d2c-108">DESCRIPTION</span></span>

<span data-ttu-id="95d2c-109">O `New-TimeSpan` cmdlet cria um objeto **TimeSpan** que representa um intervalo de tempo.</span><span class="sxs-lookup"><span data-stu-id="95d2c-109">The `New-TimeSpan` cmdlet creates a **TimeSpan** object that represents a time interval.</span></span>
<span data-ttu-id="95d2c-110">Você pode usar um objeto **TimeSpan** para adicionar ou subtrair time de objetos **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="95d2c-110">You can use a **TimeSpan** object to add or subtract time from **DateTime** objects.</span></span>

<span data-ttu-id="95d2c-111">Sem parâmetros, um `New-TimeSpan` comando retorna um objeto **TimeSpan** que representa um intervalo de tempo igual a zero.</span><span class="sxs-lookup"><span data-stu-id="95d2c-111">Without parameters, a `New-TimeSpan` command returns a **TimeSpan** object that represents a time interval of zero.</span></span>

## <span data-ttu-id="95d2c-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="95d2c-112">EXAMPLES</span></span>

### <span data-ttu-id="95d2c-113">Exemplo 1: criar um objeto TimeSpan para uma duração especificada</span><span class="sxs-lookup"><span data-stu-id="95d2c-113">Example 1: Create a TimeSpan object for a specified duration</span></span>

<span data-ttu-id="95d2c-114">Esse comando cria um objeto **TimeSpan** com uma duração de 1 hora e 25 minutos e o armazena em uma variável chamada `$TimeSpan` .</span><span class="sxs-lookup"><span data-stu-id="95d2c-114">This command creates a **TimeSpan** object with a duration of 1 hour and 25 minutes and stores it in a variable named `$TimeSpan`.</span></span> <span data-ttu-id="95d2c-115">Ele exibe uma representação do objeto **TimeSpan** .</span><span class="sxs-lookup"><span data-stu-id="95d2c-115">It displays a representation of the **TimeSpan** object.</span></span>

```powershell
$TimeSpan = New-TimeSpan -Hours 1 -Minutes 25
$TimeSpan
```

```Output
Days              : 0
Hours             : 1
Minutes           : 25
Seconds           : 0
Milliseconds      : 0
Ticks             : 51000000000
TotalDays         : 0.0590277777777778
TotalHours        : 1.41666666666667
TotalMinutes      : 85
TotalSeconds      : 5100
TotalMilliseconds : 5100000
```

### <span data-ttu-id="95d2c-116">Exemplo 2: criar um objeto TimeSpan para um intervalo de tempo</span><span class="sxs-lookup"><span data-stu-id="95d2c-116">Example 2: Create a TimeSpan object for a time interval</span></span>

<span data-ttu-id="95d2c-117">Este exemplo cria um novo objeto **TimeSpan** que representa o intervalo entre a hora em que o comando é executado e 1º de janeiro de 2010.</span><span class="sxs-lookup"><span data-stu-id="95d2c-117">This example creates a new **TimeSpan** object that represents the interval between the time that the command is run and January 1, 2010.</span></span>

<span data-ttu-id="95d2c-118">Esse comando não requer o parâmetro **Start** , pois o valor padrão do parâmetro **Start** é a data e a hora atuais.</span><span class="sxs-lookup"><span data-stu-id="95d2c-118">This command does not require the **Start** parameter, because the default value of the **Start** parameter is the current date and time.</span></span>

```powershell
New-TimeSpan -End (Get-Date -Year 2010 -Month 1 -Day 1)
```

### <span data-ttu-id="95d2c-119">Exemplo 3: obter a data de 90 dias a partir da data atual</span><span class="sxs-lookup"><span data-stu-id="95d2c-119">Example 3: Get the date 90 days from the current date</span></span>

```powershell
$90days = New-TimeSpan -Days 90
(Get-Date) + $90days
```

<span data-ttu-id="95d2c-120">Estes comandos retornam a data que é de 90 dias depois da data atual.</span><span class="sxs-lookup"><span data-stu-id="95d2c-120">These commands return the date that is 90 days after the current date.</span></span>

### <span data-ttu-id="95d2c-121">Exemplo 4: descobrir o TimeSpan desde que um arquivo foi atualizado</span><span class="sxs-lookup"><span data-stu-id="95d2c-121">Example 4: Discover the TimeSpan since a file was updated</span></span>

<span data-ttu-id="95d2c-122">Esse comando informa quanto tempo foi desde que o arquivo de ajuda [about_Remote](../Microsoft.PowerShell.Core/About/about_Remote.md) foi atualizado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="95d2c-122">This command tells you how long it has been since the [about_remote](../Microsoft.PowerShell.Core/About/about_Remote.md) help file was last updated.</span></span>
<span data-ttu-id="95d2c-123">Você pode usar esse formato de comando em qualquer arquivo ou qualquer outro objeto que tenha uma propriedade **LastWriteTime** .</span><span class="sxs-lookup"><span data-stu-id="95d2c-123">You can use this command format on any file, or any other object that has a **LastWriteTime** property.</span></span>

<span data-ttu-id="95d2c-124">Esse comando funciona porque o parâmetro **inicial** de `New-TimeSpan` tem um alias de **LastWriteTime**.</span><span class="sxs-lookup"><span data-stu-id="95d2c-124">This command works because the **Start** parameter of `New-TimeSpan` has an alias of **LastWriteTime**.</span></span> <span data-ttu-id="95d2c-125">Quando você canaliza um objeto que tem uma propriedade **LastWriteTime** para `New-TimeSpan` , o PowerShell usa o valor da propriedade **LastWriteTime** como o valor do parâmetro **Start** .</span><span class="sxs-lookup"><span data-stu-id="95d2c-125">When you pipe an object that has a **LastWriteTime** property to `New-TimeSpan`, PowerShell uses the value of the **LastWriteTime** property as the value of the **Start** parameter.</span></span>

```powershell
Get-ChildItem $PSHOME\en-us\about_remote.help.txt | New-TimeSpan
```

```Output
Days              : 321
Hours             : 21
Minutes           : 59
Seconds           : 22
Milliseconds      : 312
Ticks             : 278135623127728
TotalDays         : 321.916230471907
TotalHours        : 7725.98953132578
TotalMinutes      : 463559.371879547
TotalSeconds      : 27813562.3127728
TotalMilliseconds : 27813562312.7728
```

## <span data-ttu-id="95d2c-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="95d2c-126">PARAMETERS</span></span>

### <span data-ttu-id="95d2c-127">-Days</span><span class="sxs-lookup"><span data-stu-id="95d2c-127">-Days</span></span>

<span data-ttu-id="95d2c-128">Especifica os dias no período de tempo.</span><span class="sxs-lookup"><span data-stu-id="95d2c-128">Specifies the days in the time span.</span></span>
<span data-ttu-id="95d2c-129">O valor padrão é 0.</span><span class="sxs-lookup"><span data-stu-id="95d2c-129">The default value is 0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="95d2c-130">-Fim</span><span class="sxs-lookup"><span data-stu-id="95d2c-130">-End</span></span>

<span data-ttu-id="95d2c-131">Especifica o fim de um período de tempo.</span><span class="sxs-lookup"><span data-stu-id="95d2c-131">Specifies the end of a time span.</span></span>
<span data-ttu-id="95d2c-132">O valor padrão é a data e hora atuais.</span><span class="sxs-lookup"><span data-stu-id="95d2c-132">The default value is the current date and time.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: Date
Aliases:

Required: False
Position: 1
Default value: Current date and time
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="95d2c-133">-Horas</span><span class="sxs-lookup"><span data-stu-id="95d2c-133">-Hours</span></span>

<span data-ttu-id="95d2c-134">Especifica as horas no período de tempo.</span><span class="sxs-lookup"><span data-stu-id="95d2c-134">Specifies the hours in the time span.</span></span>
<span data-ttu-id="95d2c-135">O valor padrão é zero.</span><span class="sxs-lookup"><span data-stu-id="95d2c-135">The default value is zero.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="95d2c-136">-Minutos</span><span class="sxs-lookup"><span data-stu-id="95d2c-136">-Minutes</span></span>

<span data-ttu-id="95d2c-137">Especifica os minutos no período de tempo.</span><span class="sxs-lookup"><span data-stu-id="95d2c-137">Specifies the minutes in the time span.</span></span>
<span data-ttu-id="95d2c-138">O valor padrão é 0.</span><span class="sxs-lookup"><span data-stu-id="95d2c-138">The default value is 0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="95d2c-139">-Segundos</span><span class="sxs-lookup"><span data-stu-id="95d2c-139">-Seconds</span></span>

<span data-ttu-id="95d2c-140">Especifica o comprimento do período de tempo em segundos.</span><span class="sxs-lookup"><span data-stu-id="95d2c-140">Specifies the length of the time span in seconds.</span></span>
<span data-ttu-id="95d2c-141">O valor padrão é 0.</span><span class="sxs-lookup"><span data-stu-id="95d2c-141">The default value is 0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="95d2c-142">-Iniciar</span><span class="sxs-lookup"><span data-stu-id="95d2c-142">-Start</span></span>

<span data-ttu-id="95d2c-143">Especifica o início de um período de tempo.</span><span class="sxs-lookup"><span data-stu-id="95d2c-143">Specifies the start of a time span.</span></span>
<span data-ttu-id="95d2c-144">Insira uma cadeia de caracteres que represente a data e a hora, como "3/15/09" ou um objeto **DateTime** , como um de um `Get-Date` comando.</span><span class="sxs-lookup"><span data-stu-id="95d2c-144">Enter a string that represents the date and time, such as "3/15/09" or a **DateTime** object, such as one from a `Get-Date` command.</span></span> <span data-ttu-id="95d2c-145">O valor padrão é a data e hora atuais.</span><span class="sxs-lookup"><span data-stu-id="95d2c-145">The default value is the current date and time.</span></span>

<span data-ttu-id="95d2c-146">Você pode usar **Start** ou seu alias, **LastWriteTime**.</span><span class="sxs-lookup"><span data-stu-id="95d2c-146">You can use **Start** or its alias, **LastWriteTime**.</span></span>
<span data-ttu-id="95d2c-147">O alias **LastWriteTime** permite que você redirecione objetos que têm uma propriedade **LastWriteTime** , como arquivos no sistema de arquivos `[System.Io.FileIO]` , para o parâmetro **Start** de `New-TimeSpan` .</span><span class="sxs-lookup"><span data-stu-id="95d2c-147">The **LastWriteTime** alias lets you pipe objects that have a **LastWriteTime** property, such as files in the file system `[System.Io.FileIO]`, to the **Start** parameter of `New-TimeSpan`.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: Date
Aliases: LastWriteTime

Required: False
Position: 0
Default value: Current date and time
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="95d2c-148">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="95d2c-148">CommonParameters</span></span>

<span data-ttu-id="95d2c-149">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="95d2c-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="95d2c-150">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="95d2c-150">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="95d2c-151">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="95d2c-151">INPUTS</span></span>

### <span data-ttu-id="95d2c-152">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="95d2c-152">System.DateTime</span></span>

<span data-ttu-id="95d2c-153">É possível canalizar um objeto **DateTime** que representa essa hora de início para `New-TimeSpan` .</span><span class="sxs-lookup"><span data-stu-id="95d2c-153">You can pipe a **DateTime** object that represents that start time to `New-TimeSpan`.</span></span>

## <span data-ttu-id="95d2c-154">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="95d2c-154">OUTPUTS</span></span>

### <span data-ttu-id="95d2c-155">System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="95d2c-155">System.TimeSpan</span></span>

<span data-ttu-id="95d2c-156">`New-TimeSpan` Retorna um objeto que representa o período de tempo.</span><span class="sxs-lookup"><span data-stu-id="95d2c-156">`New-TimeSpan` returns an object that represents the time span.</span></span>

## <span data-ttu-id="95d2c-157">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="95d2c-157">NOTES</span></span>

## <span data-ttu-id="95d2c-158">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="95d2c-158">RELATED LINKS</span></span>

[<span data-ttu-id="95d2c-159">Obter Data</span><span class="sxs-lookup"><span data-stu-id="95d2c-159">Get-Date</span></span>](Get-Date.md)

[<span data-ttu-id="95d2c-160">Set-Date</span><span class="sxs-lookup"><span data-stu-id="95d2c-160">Set-Date</span></span>](Set-Date.md)

