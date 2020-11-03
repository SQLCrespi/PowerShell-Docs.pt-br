---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 4/30/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-date?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Date
ms.openlocfilehash: 1c2a029a20b80826f74662a2b68d4a5f32276b00
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193271"
---
# <span data-ttu-id="bab4f-103">Set-Date</span><span class="sxs-lookup"><span data-stu-id="bab4f-103">Set-Date</span></span>

## <span data-ttu-id="bab4f-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="bab4f-104">SYNOPSIS</span></span>
<span data-ttu-id="bab4f-105">Altera a hora do sistema no computador para uma hora que você especificar.</span><span class="sxs-lookup"><span data-stu-id="bab4f-105">Changes the system time on the computer to a time that you specify.</span></span>

## <span data-ttu-id="bab4f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bab4f-106">SYNTAX</span></span>

### <span data-ttu-id="bab4f-107">Data (padrão)</span><span class="sxs-lookup"><span data-stu-id="bab4f-107">Date (Default)</span></span>

```
Set-Date [-Date] <DateTime> [-DisplayHint <DisplayHintType>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="bab4f-108">Ajustar</span><span class="sxs-lookup"><span data-stu-id="bab4f-108">Adjust</span></span>

```
Set-Date [-Adjust] <TimeSpan> [-DisplayHint <DisplayHintType>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="bab4f-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bab4f-109">DESCRIPTION</span></span>

<span data-ttu-id="bab4f-110">O `Set-Date` cmdlet altera a data e a hora do sistema no computador para uma data e hora que você especificar.</span><span class="sxs-lookup"><span data-stu-id="bab4f-110">The `Set-Date` cmdlet changes the system date and time on the computer to a date and time that you specify.</span></span>
<span data-ttu-id="bab4f-111">Você pode especificar uma nova data e/ou hora digitando uma cadeia de caracteres ou passando um objeto **DateTime** ou **TimeSpan** para `Set-Date` .</span><span class="sxs-lookup"><span data-stu-id="bab4f-111">You can specify a new date and/or time by typing a string or by passing a **DateTime** or **TimeSpan** object to `Set-Date`.</span></span> <span data-ttu-id="bab4f-112">Para especificar uma nova data ou hora, use o parâmetro **Date** .</span><span class="sxs-lookup"><span data-stu-id="bab4f-112">To specify a new date or time, use the **Date** parameter.</span></span>
<span data-ttu-id="bab4f-113">Para especificar um intervalo de alteração, use o parâmetro **ADJUST** .</span><span class="sxs-lookup"><span data-stu-id="bab4f-113">To specify a change interval, use the **Adjust** parameter.</span></span>

## <span data-ttu-id="bab4f-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="bab4f-114">EXAMPLES</span></span>

### <span data-ttu-id="bab4f-115">Exemplo 1: adicionar três dias à data do sistema</span><span class="sxs-lookup"><span data-stu-id="bab4f-115">Example 1: Add three days to the system date</span></span>

<span data-ttu-id="bab4f-116">Este comando adiciona três dias à data do sistema atual.</span><span class="sxs-lookup"><span data-stu-id="bab4f-116">This command adds three days to the current system date.</span></span>
<span data-ttu-id="bab4f-117">Ele não afeta a hora.</span><span class="sxs-lookup"><span data-stu-id="bab4f-117">It does not affect the time.</span></span>
<span data-ttu-id="bab4f-118">O comando usa o parâmetro **Date** para especificar a data.</span><span class="sxs-lookup"><span data-stu-id="bab4f-118">The command uses the **Date** parameter to specify the date.</span></span>

<span data-ttu-id="bab4f-119">O `Get-Date` cmdlet retorna a data atual como um objeto **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="bab4f-119">The `Get-Date` cmdlet returns the current date as a **DateTime** object.</span></span> <span data-ttu-id="bab4f-120">O método **AddDays** do objeto **DateTime** adiciona um número especificado de dias (3) ao objeto **DateTime** atual.</span><span class="sxs-lookup"><span data-stu-id="bab4f-120">The **DateTime** object's **AddDays** method adds a specified number of days (3) to the current **DateTime** object.</span></span>

```powershell
Set-Date -Date (Get-Date).AddDays(3)
```

### <span data-ttu-id="bab4f-121">Exemplo 2: definir o relógio do sistema de volta 10 minutos</span><span class="sxs-lookup"><span data-stu-id="bab4f-121">Example 2: Set the system clock back 10 minutes</span></span>

<span data-ttu-id="bab4f-122">Este exemplo define a hora atual do sistema de volta por 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="bab4f-122">This example sets the current system time back by 10 minutes.</span></span>

<span data-ttu-id="bab4f-123">O parâmetro **ADJUST** permite que você especifique um intervalo de alteração (menos dez minutos) no formato de hora padrão para a localidade.</span><span class="sxs-lookup"><span data-stu-id="bab4f-123">The **Adjust** parameter allows you to specify an interval of change (minus ten minutes) in the standard time format for the locale.</span></span>

<span data-ttu-id="bab4f-124">O parâmetro **DisplayHint** informa ao PowerShell para exibir apenas a hora, mas não afeta o objeto **DateTime** que `Set-Date` retorna.</span><span class="sxs-lookup"><span data-stu-id="bab4f-124">The **DisplayHint** parameter tells PowerShell to display only the time, but it does not affect the **DateTime** object that `Set-Date` returns.</span></span>

```powershell
Set-Date -Adjust -0:10:0 -DisplayHint Time
```

### <span data-ttu-id="bab4f-125">Exemplo 3: definir a data e a hora como um valor de variável</span><span class="sxs-lookup"><span data-stu-id="bab4f-125">Example 3: Set the date and time to a variable value</span></span>

<span data-ttu-id="bab4f-126">Esses comandos alteram a data e a hora do sistema no computador local para a data e hora salvas na variável `$T` .</span><span class="sxs-lookup"><span data-stu-id="bab4f-126">These commands change the system date and time on local computer to the date and time saved in the variable `$T`.</span></span> <span data-ttu-id="bab4f-127">O primeiro comando obtém a data e a armazena em `$T` .</span><span class="sxs-lookup"><span data-stu-id="bab4f-127">The first command gets the date and stores it in `$T`.</span></span>

<span data-ttu-id="bab4f-128">O segundo comando usa o parâmetro **Date** para passar o objeto **DateTime** para `$T` o `Set-Date` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bab4f-128">The second command uses the **Date** parameter to pass the **DateTime** object in `$T` to the `Set-Date` cmdlet.</span></span>

```powershell
$T = Get-Date
Set-Date -Date $T
```

### <span data-ttu-id="bab4f-129">Exemplo 4: adicionar 90 minutos ao relógio do sistema</span><span class="sxs-lookup"><span data-stu-id="bab4f-129">Example 4: Add 90 minutes to the system clock</span></span>

<span data-ttu-id="bab4f-130">Estes comandos adiantam a hora do sistema no computador local por 90 minutos.</span><span class="sxs-lookup"><span data-stu-id="bab4f-130">These commands advance the system time on the local computer by 90 minutes.</span></span>

<span data-ttu-id="bab4f-131">O primeiro comando usa o `New-TimeSpan` cmdlet para criar um objeto **TimeSpan** com um intervalo de 90 minutos e o salva na `$90mins` variável.</span><span class="sxs-lookup"><span data-stu-id="bab4f-131">The first command uses the `New-TimeSpan` cmdlet to create a **TimeSpan** object with a 90-minute interval, and saves it in the `$90mins` variable.</span></span>

<span data-ttu-id="bab4f-132">O segundo comando usa o parâmetro **ADJUST** de `Set-Date` para ajustar a data pelo valor do objeto **TimeSpan** na `$90mins` variável.</span><span class="sxs-lookup"><span data-stu-id="bab4f-132">The second command uses the **Adjust** parameter of `Set-Date` to adjust the date by the value of the **TimeSpan** object in the `$90mins` variable.</span></span>

```powershell
$90mins = New-TimeSpan -Minutes 90
Set-Date -Adjust $90mins
```

## <span data-ttu-id="bab4f-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bab4f-133">PARAMETERS</span></span>

### <span data-ttu-id="bab4f-134">-Ajustar</span><span class="sxs-lookup"><span data-stu-id="bab4f-134">-Adjust</span></span>

<span data-ttu-id="bab4f-135">Especifica o valor para o qual este cmdlet adiciona ou subtrai da data e hora atuais.</span><span class="sxs-lookup"><span data-stu-id="bab4f-135">Specifies the value for which this cmdlet adds or subtracts from the current date and time.</span></span>
<span data-ttu-id="bab4f-136">pode digitar um ajuste no formato de data e hora padrão para sua localidade ou usar o parâmetro **ADJUST** para passar um objeto **TimeSpan** de `New-TimeSpan` para `Set-Date` .</span><span class="sxs-lookup"><span data-stu-id="bab4f-136">can type an adjustment in standard date and time format for your locale or use the **Adjust** parameter to pass a **TimeSpan** object from `New-TimeSpan` to `Set-Date`.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: Adjust
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="bab4f-137">-Data</span><span class="sxs-lookup"><span data-stu-id="bab4f-137">-Date</span></span>

<span data-ttu-id="bab4f-138">Altera a data e hora com os valores especificados.</span><span class="sxs-lookup"><span data-stu-id="bab4f-138">Changes the date and time to the specified values.</span></span>
<span data-ttu-id="bab4f-139">Você pode digitar uma nova data no formato de data abreviada e uma hora no formato de hora padrão para sua localidade.</span><span class="sxs-lookup"><span data-stu-id="bab4f-139">You can type a new date in the short date format and a time in the standard time format for your locale.</span></span> <span data-ttu-id="bab4f-140">Ou, você pode passar um objeto **DateTime** de `Get-Date` .</span><span class="sxs-lookup"><span data-stu-id="bab4f-140">Or, you can pass a **DateTime** object from `Get-Date`.</span></span>

<span data-ttu-id="bab4f-141">Se você especificar uma data, mas não uma hora, `Set-Date` o alterará o tempo de meia-noite na data especificada.</span><span class="sxs-lookup"><span data-stu-id="bab4f-141">If you specify a date, but not a time, `Set-Date` changes the time to midnight on the specified date.</span></span> <span data-ttu-id="bab4f-142">Se você especificar somente a hora, ele não altera a data.</span><span class="sxs-lookup"><span data-stu-id="bab4f-142">If you specify only a time, it does not change the date.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: Date
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="bab4f-143">-DisplayHint</span><span class="sxs-lookup"><span data-stu-id="bab4f-143">-DisplayHint</span></span>

<span data-ttu-id="bab4f-144">Especifica quais elementos da data e hora são exibidos. Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="bab4f-144">Specifies which elements of the date and time are displayed.The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="bab4f-145">Data.</span><span class="sxs-lookup"><span data-stu-id="bab4f-145">Date.</span></span>
  <span data-ttu-id="bab4f-146">exibe somente a data.</span><span class="sxs-lookup"><span data-stu-id="bab4f-146">displays only the date.</span></span>
- <span data-ttu-id="bab4f-147">Tempo.</span><span class="sxs-lookup"><span data-stu-id="bab4f-147">Time.</span></span>
  <span data-ttu-id="bab4f-148">exibe apenas a hora.</span><span class="sxs-lookup"><span data-stu-id="bab4f-148">displays only the time.</span></span>
- <span data-ttu-id="bab4f-149">DateTime.</span><span class="sxs-lookup"><span data-stu-id="bab4f-149">DateTime.</span></span>
  <span data-ttu-id="bab4f-150">exibe a data e a hora.</span><span class="sxs-lookup"><span data-stu-id="bab4f-150">displays the date and time.</span></span>

<span data-ttu-id="bab4f-151">Este parâmetro afeta somente a exibição.</span><span class="sxs-lookup"><span data-stu-id="bab4f-151">This parameter affects only the display.</span></span>
<span data-ttu-id="bab4f-152">Ele não afeta o objeto **DateTime** que o `Get-Date` recupera.</span><span class="sxs-lookup"><span data-stu-id="bab4f-152">It does not affect the **DateTime** object that `Get-Date` retrieves.</span></span>

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

### <span data-ttu-id="bab4f-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="bab4f-153">-Confirm</span></span>

<span data-ttu-id="bab4f-154">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bab4f-154">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bab4f-155">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="bab4f-155">-WhatIf</span></span>

<span data-ttu-id="bab4f-156">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="bab4f-156">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="bab4f-157">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="bab4f-157">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bab4f-158">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bab4f-158">CommonParameters</span></span>

<span data-ttu-id="bab4f-159">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bab4f-159">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bab4f-160">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="bab4f-160">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="bab4f-161">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="bab4f-161">INPUTS</span></span>

### <span data-ttu-id="bab4f-162">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="bab4f-162">System.DateTime</span></span>

<span data-ttu-id="bab4f-163">Você pode canalizar uma data para `Set-Date` .</span><span class="sxs-lookup"><span data-stu-id="bab4f-163">You can pipe a date to `Set-Date`.</span></span>

## <span data-ttu-id="bab4f-164">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="bab4f-164">OUTPUTS</span></span>

### <span data-ttu-id="bab4f-165">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="bab4f-165">System.DateTime</span></span>

<span data-ttu-id="bab4f-166">`Set-Date` Retorna um objeto que representa a data que ele definiu.</span><span class="sxs-lookup"><span data-stu-id="bab4f-166">`Set-Date` returns an object that represents the date that it set.</span></span>

## <span data-ttu-id="bab4f-167">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="bab4f-167">NOTES</span></span>

- <span data-ttu-id="bab4f-168">Use esse cmdlet com cuidado ao alterar a data e a hora do computador.</span><span class="sxs-lookup"><span data-stu-id="bab4f-168">Use this cmdlet cautiously when changing the date and time on the computer.</span></span> <span data-ttu-id="bab4f-169">A alteração pode impedir que o computador receba eventos de todo o sistema e atualizações que são disparadas por uma data ou hora.</span><span class="sxs-lookup"><span data-stu-id="bab4f-169">The change might prevent the computer from receiving system-wide events and updates that are triggered by a date or time.</span></span> <span data-ttu-id="bab4f-170">Use os parâmetros **WhatIf** e **Confirm** para evitar erros.</span><span class="sxs-lookup"><span data-stu-id="bab4f-170">Use the **WhatIf** and **Confirm** parameters to avoid errors.</span></span>
- <span data-ttu-id="bab4f-171">Você pode usar métodos padrão do .NET com os objetos **DateTime** e **TimeSpan** usados com o `Set-Date` , como **subdias** , **AddMonths** e **FromFileTime** .</span><span class="sxs-lookup"><span data-stu-id="bab4f-171">You can use standard .NET methods with the **DateTime** and **TimeSpan** objects used with `Set-Date`, such as **AddDays** , **AddMonths** , and **FromFileTime** .</span></span> <span data-ttu-id="bab4f-172">Para obter mais informações, consulte [métodos DateTime](/dotnet/api/system.datetime) e</span><span class="sxs-lookup"><span data-stu-id="bab4f-172">For more information, see [DateTime Methods](/dotnet/api/system.datetime) and</span></span>

  <span data-ttu-id="bab4f-173">[Métodos TimeSpan](/dotnet/api/system.timespan) na biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="bab4f-173">[TimeSpan Methods](/dotnet/api/system.timespan) in the MSDN library.</span></span>

## <span data-ttu-id="bab4f-174">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="bab4f-174">RELATED LINKS</span></span>

[<span data-ttu-id="bab4f-175">Obter Data</span><span class="sxs-lookup"><span data-stu-id="bab4f-175">Get-Date</span></span>](Get-Date.md)

[<span data-ttu-id="bab4f-176">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="bab4f-176">New-TimeSpan</span></span>](New-TimeSpan.md)

