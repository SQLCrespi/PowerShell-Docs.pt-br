---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/01/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-culture?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Culture
ms.openlocfilehash: dc49f153adc22b7c2c943a4cc529ac155561228a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596797"
---
# <span data-ttu-id="c5058-102">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="c5058-102">Get-Culture</span></span>

## <span data-ttu-id="c5058-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="c5058-103">SYNOPSIS</span></span>
<span data-ttu-id="c5058-104">Obtém a cultura atual definida no sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="c5058-104">Gets the current culture set in the operating system.</span></span>

## <span data-ttu-id="c5058-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c5058-105">SYNTAX</span></span>

### <span data-ttu-id="c5058-106">CurrentCulture (padrão)</span><span class="sxs-lookup"><span data-stu-id="c5058-106">CurrentCulture (Default)</span></span>

```
Get-Culture [-NoUserOverrides] [<CommonParameters>]
```

### <span data-ttu-id="c5058-107">Nome</span><span class="sxs-lookup"><span data-stu-id="c5058-107">Name</span></span>

```
Get-Culture [-Name <String[]>] [-NoUserOverrides] [<CommonParameters>]
```

### <span data-ttu-id="c5058-108">ListAvailable</span><span class="sxs-lookup"><span data-stu-id="c5058-108">ListAvailable</span></span>

```
Get-Culture [-ListAvailable] [<CommonParameters>]
```

## <span data-ttu-id="c5058-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c5058-109">DESCRIPTION</span></span>

<span data-ttu-id="c5058-110">O `Get-Culture` cmdlet obtém informações sobre as configurações de cultura atuais.</span><span class="sxs-lookup"><span data-stu-id="c5058-110">The `Get-Culture` cmdlet gets information about the current culture settings.</span></span> <span data-ttu-id="c5058-111">Isso inclui informações sobre as configurações de idioma atuais no sistema, como o layout do teclado e o formato de exibição de itens como números, moeda e datas.</span><span class="sxs-lookup"><span data-stu-id="c5058-111">This includes information about the current language settings on the system, such as the keyboard layout, and the display format of items such as numbers, currency, and dates.</span></span>

<span data-ttu-id="c5058-112">Você também pode usar o `Get-UICulture` cmdlet, que obtém a cultura da interface do usuário atual no sistema e o cmdlet [set-Culture](/powershell/module/international/set-culture) no módulo internacional.</span><span class="sxs-lookup"><span data-stu-id="c5058-112">You can also use the `Get-UICulture` cmdlet, which gets the current user interface culture on the system, and the [Set-Culture](/powershell/module/international/set-culture) cmdlet in the International module.</span></span> <span data-ttu-id="c5058-113">A cultura da interface do usuário determina quais cadeias de caracteres de texto serão usadas para elementos de interface do usuário, como menus e mensagens.</span><span class="sxs-lookup"><span data-stu-id="c5058-113">The user-interface (UI) culture determines which text strings are used for user interface elements, such as menus and messages.</span></span>

## <span data-ttu-id="c5058-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="c5058-114">EXAMPLES</span></span>

### <span data-ttu-id="c5058-115">Exemplo 1: obter configurações de cultura</span><span class="sxs-lookup"><span data-stu-id="c5058-115">Example 1: Get culture settings</span></span>

```powershell
Get-Culture
```

```Output
LCID             Name             DisplayName
----             ----             -----------
1033             en-US            English (United States)
```

<span data-ttu-id="c5058-116">Este comando exibe informações sobre as configurações regionais do computador.</span><span class="sxs-lookup"><span data-stu-id="c5058-116">This command displays information about the regional settings on the computer.</span></span>

### <span data-ttu-id="c5058-117">Exemplo 2: Formatar as propriedades de um objeto de cultura</span><span class="sxs-lookup"><span data-stu-id="c5058-117">Example 2: Format the properties of a culture object</span></span>

```powershell
PS C:\> $C = Get-Culture
PS C:\> $C | Format-List -Property *
Parent                         : en
LCID                           : 1033
KeyboardLayoutId               : 1033
Name                           : en-US
IetfLanguageTag                : en-US
DisplayName                    : English (United States)
NativeName                     : English (United States)
EnglishName                    : English (United States)
TwoLetterISOLanguageName       : en
ThreeLetterISOLanguageName     : eng
ThreeLetterWindowsLanguageName : ENU
CompareInfo                    : CompareInfo - 1033
TextInfo                       : TextInfo - 1033
IsNeutralCulture               : False
CultureTypes                   : SpecificCultures, InstalledWin32Cultures, FrameworkCultures
NumberFormat                   : System.Globalization.NumberFormatInfo
DateTimeFormat                 : System.Globalization.DateTimeFormatInfo
Calendar                       : System.Globalization.GregorianCalendar
OptionalCalendars              : {System.Globalization.GregorianCalendar, System.Globalization.GregorianCalendar}
UseUserOverride                : True
IsReadOnly                     : False

PS C:\> $C.Calendar
MinSupportedDateTime : 1/1/0001 12:00:00 AM
MaxSupportedDateTime : 12/31/9999 11:59:59 PM
AlgorithmType        : SolarCalendar
CalendarType         : Localized
Eras                 : {1}
TwoDigitYearMax      : 2029
IsReadOnly           : False

PS C:\> $C.DateTimeFormat
AMDesignator                     : AM
Calendar                         : System.Globalization.GregorianCalendar
DateSeparator                    : /
FirstDayOfWeek                   : Sunday
CalendarWeekRule                 : FirstDay
FullDateTimePattern              : dddd, MMMM dd, yyyy h:mm:ss tt
LongDatePattern                  : dddd, MMMM dd, yyyy
LongTimePattern                  : h:mm:ss tt
MonthDayPattern                  : MMMM dd
PMDesignator                     : PM
RFC1123Pattern                   : ddd, dd MMM yyyy HH':'mm':'ss 'GMT'
ShortDatePattern                 : M/d/yyyy
ShortTimePattern                 : h:mm tt
SortableDateTimePattern          : yyyy'-'MM'-'dd'T'HH':'mm':'ss
TimeSeparator                    : :
UniversalSortableDateTimePattern : yyyy'-'MM'-'dd HH':'mm':'ss'Z'
YearMonthPattern                 : MMMM, yyyy
AbbreviatedDayNames              : {Sun, Mon, Tue, Wed...}
ShortestDayNames                 : {Su, Mo, Tu, We...}
DayNames                         : {Sunday, Monday, Tuesday, Wednesday...}
AbbreviatedMonthNames            : {Jan, Feb, Mar, Apr...}
MonthNames                       : {January, February, March, April...}
IsReadOnly                       : False
NativeCalendarName               : Gregorian Calendar
AbbreviatedMonthGenitiveNames    : {Jan, Feb, Mar, Apr...}
MonthGenitiveNames               : {January, February, March, April...}

PS C:\> $C.DateTimeFormat.FirstDayOfWeek
Sunday
```

<span data-ttu-id="c5058-118">Este exemplo demonstra a enorme quantidade de dados do objeto de cultura.</span><span class="sxs-lookup"><span data-stu-id="c5058-118">This example demonstrates the vast amount of data in the culture object.</span></span> <span data-ttu-id="c5058-119">Ele mostra como exibir as propriedades e subpropriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="c5058-119">It shows how to display the properties and sub-properties of the object.</span></span>

<span data-ttu-id="c5058-120">O primeiro comando usa o `Get-Culture` cmdlet para obter as configurações de cultura atuais no computador.</span><span class="sxs-lookup"><span data-stu-id="c5058-120">The first command uses the `Get-Culture` cmdlet to get the current culture settings on the computer.</span></span>
<span data-ttu-id="c5058-121">Ele armazena o objeto de cultura resultante na `$C` variável.</span><span class="sxs-lookup"><span data-stu-id="c5058-121">It stores the resulting culture object in the `$C` variable.</span></span>

<span data-ttu-id="c5058-122">O segundo comando exibe todas as propriedades do objeto de cultura.</span><span class="sxs-lookup"><span data-stu-id="c5058-122">The second command displays all of the properties of the culture object.</span></span> <span data-ttu-id="c5058-123">Ele usa um operador de pipeline ( `|` ) para enviar o objeto de cultura `$C` para o `Format-List` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c5058-123">It uses a pipeline operator (`|`) to send the culture object in `$C` to the `Format-List` cmdlet.</span></span> <span data-ttu-id="c5058-124">Ele usa o parâmetro **Property** para exibir todas as `*` Propriedades () do objeto.</span><span class="sxs-lookup"><span data-stu-id="c5058-124">It uses the **Property** parameter to display all (`*`) properties of the object.</span></span> <span data-ttu-id="c5058-125">Esse comando pode ser abreviado como `$c | fl *` .</span><span class="sxs-lookup"><span data-stu-id="c5058-125">This command can be abbreviated as `$c | fl *`.</span></span>

<span data-ttu-id="c5058-126">Os comandos restantes exploram as propriedades do objeto cultura usando a notação de ponto para exibir os valores das propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="c5058-126">The remaining commands explore the properties of the culture object by using dot notation to display the values of the object properties.</span></span> <span data-ttu-id="c5058-127">Você pode usar essa notação para exibir o valor de qualquer propriedade do objeto.</span><span class="sxs-lookup"><span data-stu-id="c5058-127">You can use this notation to display the value of any property of the object.</span></span>

<span data-ttu-id="c5058-128">O terceiro comando usa a notação de ponto para exibir o valor da propriedade **Calendar** do objeto Culture.</span><span class="sxs-lookup"><span data-stu-id="c5058-128">The third command uses dot notation to display the value of the **Calendar** property of the culture object.</span></span>

<span data-ttu-id="c5058-129">O quarto comando usa a notação de ponto para exibir o valor da propriedade **DataTimeFormat** do objeto Culture.</span><span class="sxs-lookup"><span data-stu-id="c5058-129">The fourth command uses dot notation to display the value of the **DataTimeFormat** property of the culture object.</span></span>

<span data-ttu-id="c5058-130">Muitas propriedades de objeto têm propriedades.</span><span class="sxs-lookup"><span data-stu-id="c5058-130">Many object properties have properties.</span></span> <span data-ttu-id="c5058-131">O quinto comando usa a notação de ponto para exibir o valor da propriedade **FirstDayOfWeek** da propriedade **DateTimeFormat** .</span><span class="sxs-lookup"><span data-stu-id="c5058-131">The fifth command uses dot notation to display the value of the **FirstDayOfWeek** property of the **DateTimeFormat** property.</span></span>

### <span data-ttu-id="c5058-132">Exemplo 3: obter uma cultura específica</span><span class="sxs-lookup"><span data-stu-id="c5058-132">Example 3: Get a specific culture</span></span>

<span data-ttu-id="c5058-133">Obtenha o objeto CultureInfo para francês na França.</span><span class="sxs-lookup"><span data-stu-id="c5058-133">Get the CultureInfo object for French in France.</span></span>

```powershell
Get-Culture -Name fr-FR
```

```Output
LCID             Name             DisplayName
----             ----             -----------
1036             fr-FR            French (France)
```

## <span data-ttu-id="c5058-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c5058-134">PARAMETERS</span></span>

### <span data-ttu-id="c5058-135">-ListAvailable</span><span class="sxs-lookup"><span data-stu-id="c5058-135">-ListAvailable</span></span>

<span data-ttu-id="c5058-136">Recupera todas as culturas suportadas pelo sistema operacional atual.</span><span class="sxs-lookup"><span data-stu-id="c5058-136">Retrieves all cultures supported by the current operating system.</span></span>

<span data-ttu-id="c5058-137">Esse parâmetro foi introduzido no PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="c5058-137">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ListAvailable
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c5058-138">-Name</span><span class="sxs-lookup"><span data-stu-id="c5058-138">-Name</span></span>

<span data-ttu-id="c5058-139">Recupere uma cultura específica com base no nome.</span><span class="sxs-lookup"><span data-stu-id="c5058-139">Retrieve a specific culture based on the name.</span></span>

<span data-ttu-id="c5058-140">Esse parâmetro foi introduzido no PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="c5058-140">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c5058-141">-NoUserOverrides</span><span class="sxs-lookup"><span data-stu-id="c5058-141">-NoUserOverrides</span></span>

<span data-ttu-id="c5058-142">Ignorar alterações de usuário para a cultura atual.</span><span class="sxs-lookup"><span data-stu-id="c5058-142">Ignore user changes for current culture.</span></span>

<span data-ttu-id="c5058-143">Esse parâmetro foi introduzido no PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="c5058-143">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CurrentCulture, Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c5058-144">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c5058-144">CommonParameters</span></span>

<span data-ttu-id="c5058-145">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c5058-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c5058-146">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c5058-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c5058-147">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="c5058-147">INPUTS</span></span>

### <span data-ttu-id="c5058-148">Nenhum</span><span class="sxs-lookup"><span data-stu-id="c5058-148">None</span></span>

<span data-ttu-id="c5058-149">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c5058-149">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="c5058-150">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="c5058-150">OUTPUTS</span></span>

### <span data-ttu-id="c5058-151">System. Globalization. CultureInfo</span><span class="sxs-lookup"><span data-stu-id="c5058-151">System.Globalization.CultureInfo</span></span>

<span data-ttu-id="c5058-152">`Get-Culture` Retorna um objeto que representa a cultura atual.</span><span class="sxs-lookup"><span data-stu-id="c5058-152">`Get-Culture` returns an object that represents the current culture.</span></span>

## <span data-ttu-id="c5058-153">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="c5058-153">NOTES</span></span>

<span data-ttu-id="c5058-154">Você também pode usar as `$PsCulture` `$PsUICulture` variáveis e.</span><span class="sxs-lookup"><span data-stu-id="c5058-154">You can also use the `$PsCulture` and `$PsUICulture` variables.</span></span> <span data-ttu-id="c5058-155">A `$PsCulture` variável armazena o nome da cultura atual e a `$PsUICulture` variável armazena o nome da cultura da interface do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="c5058-155">The `$PsCulture` variable stores the name of the current culture and the `$PsUICulture` variable stores the name of the current UI culture.</span></span>

## <span data-ttu-id="c5058-156">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="c5058-156">RELATED LINKS</span></span>

[<span data-ttu-id="c5058-157">Set-Culture</span><span class="sxs-lookup"><span data-stu-id="c5058-157">Set-Culture</span></span>](/powershell/module/international/set-culture)

[<span data-ttu-id="c5058-158">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="c5058-158">Get-UICulture</span></span>](Get-UICulture.md)
