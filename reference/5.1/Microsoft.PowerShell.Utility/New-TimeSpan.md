---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/1/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-timespan?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-TimeSpan
ms.openlocfilehash: 89f277f658645f18d0ae5f2f3ad0e81a8fbdb4a6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193765"
---
# <span data-ttu-id="ab3ad-103">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="ab3ad-103">New-TimeSpan</span></span>

## <span data-ttu-id="ab3ad-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="ab3ad-104">SYNOPSIS</span></span>
<span data-ttu-id="ab3ad-105">Cria um objeto TimeSpan.</span><span class="sxs-lookup"><span data-stu-id="ab3ad-105">Creates a TimeSpan object.</span></span>

## <span data-ttu-id="ab3ad-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ab3ad-106">SYNTAX</span></span>

### <span data-ttu-id="ab3ad-107">Data (padrão)</span><span class="sxs-lookup"><span data-stu-id="ab3ad-107">Date (Default)</span></span>

```
New-TimeSpan [[-Start] <DateTime>] [[-End] <DateTime>] [<CommonParameters>]
```

### <span data-ttu-id="ab3ad-108">Tempo</span><span class="sxs-lookup"><span data-stu-id="ab3ad-108">Time</span></span>

```
New-TimeSpan [-Days <Int32>] [-Hours <Int32>] [-Minutes <Int32>] [-Seconds <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="ab3ad-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ab3ad-109">DESCRIPTION</span></span>

<span data-ttu-id="ab3ad-110">O `New-TimeSpan` cmdlet cria um objeto **TimeSpan** que representa um intervalo de tempo.</span><span class="sxs-lookup"><span data-stu-id="ab3ad-110">The `New-TimeSpan` cmdlet creates a **TimeSpan** object that represents a time interval.</span></span>
<span data-ttu-id="ab3ad-111">Você pode usar um objeto **TimeSpan** para adicionar ou subtrair time de objetos **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="ab3ad-111">You can use a **TimeSpan** object to add or subtract time from **DateTime** objects.</span></span>

<span data-ttu-id="ab3ad-112">Sem parâmetros, um `New-TimeSpan` comando retorna um objeto **TimeSpan** que representa um intervalo de tempo igual a zero.</span><span class="sxs-lookup"><span data-stu-id="ab3ad-112">Without parameters, a `New-TimeSpan` command returns a **TimeSpan** object that represents a time interval of zero.</span></span>

## <span data-ttu-id="ab3ad-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="ab3ad-113">EXAMPLES</span></span>

### <span data-ttu-id="ab3ad-114">Exemplo 1: criar um objeto TimeSpan para uma duração especificada</span><span class="sxs-lookup"><span data-stu-id="ab3ad-114">Example 1: Create a TimeSpan object for a specified duration</span></span>

<span data-ttu-id="ab3ad-115">Esse comando cria um objeto **TimeSpan** com uma duração de 1 hora e 25 minutos e o armazena em uma variável chamada `$TimeSpan` .</span><span class="sxs-lookup"><span data-stu-id="ab3ad-115">This command creates a **TimeSpan** object with a duration of 1 hour and 25 minutes and stores it in a variable named `$TimeSpan`.</span></span> <span data-ttu-id="ab3ad-116">Ele exibe uma representação do objeto **TimeSpan** .</span><span class="sxs-lookup"><span data-stu-id="ab3ad-116">It displays a representation of the **TimeSpan** object.</span></span>

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

### <span data-ttu-id="ab3ad-117">Exemplo 2: criar um objeto TimeSpan para um intervalo de tempo</span><span class="sxs-lookup"><span data-stu-id="ab3ad-117">Example 2: Create a TimeSpan object for a time interval</span></span>

<span data-ttu-id="ab3ad-118">Este exemplo cria um novo objeto **TimeSpan** que representa o intervalo entre a hora em que o comando é executado e 1º de janeiro de 2010.</span><span class="sxs-lookup"><span data-stu-id="ab3ad-118">This example creates a new **TimeSpan** object that represents the interval between the time that the command is run and January 1, 2010.</span></span>

<span data-ttu-id="ab3ad-119">Esse comando não requer o parâmetro **Start** , pois o valor padrão do parâmetro **Start** é a data e a hora atuais.</span><span class="sxs-lookup"><span data-stu-id="ab3ad-119">This command does not require the **Start** parameter, because the default value of the **Start** parameter is the current date and time.</span></span>

```powershell
New-TimeSpan -End (Get-Date -Year 2010 -Month 1 -Day 1)
```

### <span data-ttu-id="ab3ad-120">Exemplo 3: obter a data de 90 dias a partir da data atual</span><span class="sxs-lookup"><span data-stu-id="ab3ad-120">Example 3: Get the date 90 days from the current date</span></span>

```powershell
$90days = New-TimeSpan -Days 90
(Get-Date) + $90days
```

<span data-ttu-id="ab3ad-121">Estes comandos retornam a data que é de 90 dias depois da data atual.</span><span class="sxs-lookup"><span data-stu-id="ab3ad-121">These commands return the date that is 90 days after the current date.</span></span>

### <span data-ttu-id="ab3ad-122">Exemplo 4: descobrir o TimeSpan desde que um arquivo foi atualizado</span><span class="sxs-lookup"><span data-stu-id="ab3ad-122">Example 4: Discover the TimeSpan since a file was updated</span></span>

<span data-ttu-id="ab3ad-123">Esse comando informa quanto tempo foi desde que o arquivo de ajuda [about_Remote](../Microsoft.PowerShell.Core/About/about_Remote.md) foi atualizado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="ab3ad-123">This command tells you how long it has been since the [about_remote](../Microsoft.PowerShell.Core/About/about_Remote.md) help file was last updated.</span></span>
<span data-ttu-id="ab3ad-124">Você pode usar esse formato de comando em qualquer arquivo ou qualquer outro objeto que tenha uma propriedade **LastWriteTime** .</span><span class="sxs-lookup"><span data-stu-id="ab3ad-124">You can use this command format on any file, or any other object that has a **LastWriteTime** property.</span></span>

<span data-ttu-id="ab3ad-125">Esse comando funciona porque o parâmetro **inicial** de `New-TimeSpan` tem um alias de **LastWriteTime** .</span><span class="sxs-lookup"><span data-stu-id="ab3ad-125">This command works because the **Start** parameter of `New-TimeSpan` has an alias of **LastWriteTime** .</span></span> <span data-ttu-id="ab3ad-126">Quando você canaliza um objeto que tem uma propriedade **LastWriteTime** para `New-TimeSpan` , o PowerShell usa o valor da propriedade **LastWriteTime** como o valor do parâmetro **Start** .</span><span class="sxs-lookup"><span data-stu-id="ab3ad-126">When you pipe an object that has a **LastWriteTime** property to `New-TimeSpan`, PowerShell uses the value of the **LastWriteTime** property as the value of the **Start** parameter.</span></span>

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

## <span data-ttu-id="ab3ad-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ab3ad-127">PARAMETERS</span></span>

### <span data-ttu-id="ab3ad-128">-Days</span><span class="sxs-lookup"><span data-stu-id="ab3ad-128">-Days</span></span>

<span data-ttu-id="ab3ad-129">Especifica os dias no período de tempo.</span><span class="sxs-lookup"><span data-stu-id="ab3ad-129">Specifies the days in the time span.</span></span>
<span data-ttu-id="ab3ad-130">O valor padrão é 0.</span><span class="sxs-lookup"><span data-stu-id="ab3ad-130">The default value is 0.</span></span>

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

### <span data-ttu-id="ab3ad-131">-Fim</span><span class="sxs-lookup"><span data-stu-id="ab3ad-131">-End</span></span>

<span data-ttu-id="ab3ad-132">Especifica o fim de um período de tempo.</span><span class="sxs-lookup"><span data-stu-id="ab3ad-132">Specifies the end of a time span.</span></span>
<span data-ttu-id="ab3ad-133">O valor padrão é a data e hora atuais.</span><span class="sxs-lookup"><span data-stu-id="ab3ad-133">The default value is the current date and time.</span></span>

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

### <span data-ttu-id="ab3ad-134">-Horas</span><span class="sxs-lookup"><span data-stu-id="ab3ad-134">-Hours</span></span>

<span data-ttu-id="ab3ad-135">Especifica as horas no período de tempo.</span><span class="sxs-lookup"><span data-stu-id="ab3ad-135">Specifies the hours in the time span.</span></span>
<span data-ttu-id="ab3ad-136">O valor padrão é zero.</span><span class="sxs-lookup"><span data-stu-id="ab3ad-136">The default value is zero.</span></span>

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

### <span data-ttu-id="ab3ad-137">-Minutos</span><span class="sxs-lookup"><span data-stu-id="ab3ad-137">-Minutes</span></span>

<span data-ttu-id="ab3ad-138">Especifica os minutos no período de tempo.</span><span class="sxs-lookup"><span data-stu-id="ab3ad-138">Specifies the minutes in the time span.</span></span>
<span data-ttu-id="ab3ad-139">O valor padrão é 0.</span><span class="sxs-lookup"><span data-stu-id="ab3ad-139">The default value is 0.</span></span>

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

### <span data-ttu-id="ab3ad-140">-Segundos</span><span class="sxs-lookup"><span data-stu-id="ab3ad-140">-Seconds</span></span>

<span data-ttu-id="ab3ad-141">Especifica o comprimento do período de tempo em segundos.</span><span class="sxs-lookup"><span data-stu-id="ab3ad-141">Specifies the length of the time span in seconds.</span></span>
<span data-ttu-id="ab3ad-142">O valor padrão é 0.</span><span class="sxs-lookup"><span data-stu-id="ab3ad-142">The default value is 0.</span></span>

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

### <span data-ttu-id="ab3ad-143">-Iniciar</span><span class="sxs-lookup"><span data-stu-id="ab3ad-143">-Start</span></span>

<span data-ttu-id="ab3ad-144">Especifica o início de um período de tempo.</span><span class="sxs-lookup"><span data-stu-id="ab3ad-144">Specifies the start of a time span.</span></span>
<span data-ttu-id="ab3ad-145">Insira uma cadeia de caracteres que represente a data e a hora, como "3/15/09" ou um objeto **DateTime** , como um de um `Get-Date` comando.</span><span class="sxs-lookup"><span data-stu-id="ab3ad-145">Enter a string that represents the date and time, such as "3/15/09" or a **DateTime** object, such as one from a `Get-Date` command.</span></span> <span data-ttu-id="ab3ad-146">O valor padrão é a data e hora atuais.</span><span class="sxs-lookup"><span data-stu-id="ab3ad-146">The default value is the current date and time.</span></span>

<span data-ttu-id="ab3ad-147">Você pode usar **Start** ou seu alias, **LastWriteTime** .</span><span class="sxs-lookup"><span data-stu-id="ab3ad-147">You can use **Start** or its alias, **LastWriteTime** .</span></span>
<span data-ttu-id="ab3ad-148">O alias **LastWriteTime** permite que você redirecione objetos que têm uma propriedade **LastWriteTime** , como arquivos no sistema de arquivos `[System.Io.FileIO]` , para o parâmetro **Start** de `New-TimeSpan` .</span><span class="sxs-lookup"><span data-stu-id="ab3ad-148">The **LastWriteTime** alias lets you pipe objects that have a **LastWriteTime** property, such as files in the file system `[System.Io.FileIO]`, to the **Start** parameter of `New-TimeSpan`.</span></span>

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

### <span data-ttu-id="ab3ad-149">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ab3ad-149">CommonParameters</span></span>

<span data-ttu-id="ab3ad-150">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ab3ad-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ab3ad-151">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="ab3ad-151">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="ab3ad-152">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="ab3ad-152">INPUTS</span></span>

### <span data-ttu-id="ab3ad-153">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="ab3ad-153">System.DateTime</span></span>

<span data-ttu-id="ab3ad-154">É possível canalizar um objeto **DateTime** que representa essa hora de início para `New-TimeSpan` .</span><span class="sxs-lookup"><span data-stu-id="ab3ad-154">You can pipe a **DateTime** object that represents that start time to `New-TimeSpan`.</span></span>

## <span data-ttu-id="ab3ad-155">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="ab3ad-155">OUTPUTS</span></span>

### <span data-ttu-id="ab3ad-156">System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="ab3ad-156">System.TimeSpan</span></span>

<span data-ttu-id="ab3ad-157">`New-TimeSpan` Retorna um objeto que representa o período de tempo.</span><span class="sxs-lookup"><span data-stu-id="ab3ad-157">`New-TimeSpan` returns an object that represents the time span.</span></span>

## <span data-ttu-id="ab3ad-158">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="ab3ad-158">NOTES</span></span>

## <span data-ttu-id="ab3ad-159">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="ab3ad-159">RELATED LINKS</span></span>

[<span data-ttu-id="ab3ad-160">Obter Data</span><span class="sxs-lookup"><span data-stu-id="ab3ad-160">Get-Date</span></span>](Get-Date.md)

[<span data-ttu-id="ab3ad-161">Set-Date</span><span class="sxs-lookup"><span data-stu-id="ab3ad-161">Set-Date</span></span>](Set-Date.md)
