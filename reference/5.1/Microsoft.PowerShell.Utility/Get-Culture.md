---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-culture?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Culture
ms.openlocfilehash: d7e9ebd56db3ad9de2bfbcec62f73f1f8c0e2eaa
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "93192602"
---
# <span data-ttu-id="b991b-103">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="b991b-103">Get-Culture</span></span>

## <span data-ttu-id="b991b-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b991b-104">SYNOPSIS</span></span>
<span data-ttu-id="b991b-105">Obtém a cultura atual definida no sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="b991b-105">Gets the current culture set in the operating system.</span></span>

## <span data-ttu-id="b991b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b991b-106">SYNTAX</span></span>

```
Get-Culture [<CommonParameters>]
```

## <span data-ttu-id="b991b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b991b-107">DESCRIPTION</span></span>
<span data-ttu-id="b991b-108">O cmdlet **Get-Culture** Obtém informações sobre as configurações de cultura atuais.</span><span class="sxs-lookup"><span data-stu-id="b991b-108">The **Get-Culture** cmdlet gets information about the current culture settings.</span></span>
<span data-ttu-id="b991b-109">Isso inclui informações sobre as configurações de idioma atuais no sistema, como o layout do teclado e o formato de exibição de itens como números, moeda e datas.</span><span class="sxs-lookup"><span data-stu-id="b991b-109">This includes information about the current language settings on the system, such as the keyboard layout, and the display format of items such as numbers, currency, and dates.</span></span>

<span data-ttu-id="b991b-110">Você também pode usar o cmdlet Get-UICulture, que obtém a cultura da interface do usuário atual no sistema e o cmdlet [set-Culture](https://go.microsoft.com/fwlink/?LinkID=242258) no módulo internacional.</span><span class="sxs-lookup"><span data-stu-id="b991b-110">You can also use the Get-UICulture cmdlet, which gets the current user interface culture on the system, and the [Set-Culture](https://go.microsoft.com/fwlink/?LinkID=242258) cmdlet in the International module.</span></span>
<span data-ttu-id="b991b-111">A cultura da interface do usuário determina quais cadeias de caracteres de texto serão usadas para elementos de interface do usuário, como menus e mensagens.</span><span class="sxs-lookup"><span data-stu-id="b991b-111">The user-interface (UI) culture determines which text strings are used for user interface elements, such as menus and messages.</span></span>

## <span data-ttu-id="b991b-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b991b-112">EXAMPLES</span></span>

### <span data-ttu-id="b991b-113">Exemplo 1: obter configurações de cultura</span><span class="sxs-lookup"><span data-stu-id="b991b-113">Example 1: Get culture settings</span></span>

```
PS C:\> Get-Culture
```

<span data-ttu-id="b991b-114">Este comando exibe informações sobre as configurações regionais do computador.</span><span class="sxs-lookup"><span data-stu-id="b991b-114">This command displays information about the regional settings on the computer.</span></span>

### <span data-ttu-id="b991b-115">Exemplo 2: Formatar as propriedades de um objeto de cultura</span><span class="sxs-lookup"><span data-stu-id="b991b-115">Example 2: Format the properties of a culture object</span></span>

```
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
IsReadOnly                     : False PS C:\> $C.Calendar
MinSupportedDateTime : 1/1/0001 12:00:00 AM
MaxSupportedDateTime : 12/31/9999 11:59:59 PM
AlgorithmType        : SolarCalendar
CalendarType         : Localized
Eras                 : {1}
TwoDigitYearMax      : 2029
IsReadOnly           : False PS C:\> $C.DateTimeFormat
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
MonthGenitiveNames               : {January, February, March, April...} PS C:\> $C.DateTimeFormat.FirstDayOfWeek
Sunday
```

<span data-ttu-id="b991b-116">Este exemplo demonstra a enorme quantidade de dados do objeto de cultura.</span><span class="sxs-lookup"><span data-stu-id="b991b-116">This example demonstrates the vast amount of data in the culture object.</span></span>
<span data-ttu-id="b991b-117">Ele mostra como exibir as propriedades e subpropriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="b991b-117">It shows how to display the properties and sub-properties of the object.</span></span>

<span data-ttu-id="b991b-118">O primeiro comando usa o cmdlet **Get-Culture** para obter as configurações de cultura atuais no computador.</span><span class="sxs-lookup"><span data-stu-id="b991b-118">The first command uses the **Get-Culture** cmdlet to get the current culture settings on the computer.</span></span>
<span data-ttu-id="b991b-119">Ele armazena o objeto de cultura resultante na variável $C.</span><span class="sxs-lookup"><span data-stu-id="b991b-119">It stores the resulting culture object in the $C variable.</span></span>

<span data-ttu-id="b991b-120">O segundo comando exibe todas as propriedades do objeto de cultura.</span><span class="sxs-lookup"><span data-stu-id="b991b-120">The second command displays all of the properties of the culture object.</span></span>
<span data-ttu-id="b991b-121">Ele usa um operador de pipeline (|) para enviar o objeto de cultura em $C para o cmdlet Format-List.</span><span class="sxs-lookup"><span data-stu-id="b991b-121">It uses a pipeline operator (|) to send the culture object in $C to the Format-List cmdlet.</span></span>
<span data-ttu-id="b991b-122">Ele usa o parâmetro *Property* para exibir todas as propriedades (\*) do objeto.</span><span class="sxs-lookup"><span data-stu-id="b991b-122">It uses the *Property* parameter to display all (\*) properties of the object.</span></span>
<span data-ttu-id="b991b-123">Esse comando pode ser abreviado como `$c | fl *` .</span><span class="sxs-lookup"><span data-stu-id="b991b-123">This command can be abbreviated as `$c | fl *`.</span></span>

<span data-ttu-id="b991b-124">Os comandos restantes exploram as propriedades do objeto cultura usando a notação de ponto para exibir os valores das propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="b991b-124">The remaining commands explore the properties of the culture object by using dot notation to display the values of the object properties.</span></span>
<span data-ttu-id="b991b-125">Você pode usar essa notação para exibir o valor de qualquer propriedade do objeto.</span><span class="sxs-lookup"><span data-stu-id="b991b-125">You can use this notation to display the value of any property of the object.</span></span>

<span data-ttu-id="b991b-126">O terceiro comando usa a notação de ponto para exibir o valor da propriedade Calendar do objeto cultura.</span><span class="sxs-lookup"><span data-stu-id="b991b-126">The third command uses dot notation to display the value of the Calendar property of the culture object.</span></span>

<span data-ttu-id="b991b-127">O quarto comando usa a notação de ponto para exibir o valor da propriedade DataTimeFormat do objeto cultura.</span><span class="sxs-lookup"><span data-stu-id="b991b-127">The fourth command uses dot notation to display the value of the DataTimeFormat property of the culture object.</span></span>

<span data-ttu-id="b991b-128">Muitas propriedades de objeto têm propriedades.</span><span class="sxs-lookup"><span data-stu-id="b991b-128">Many object properties have properties.</span></span>
<span data-ttu-id="b991b-129">O quinto comando usa a notação de ponto para exibir o valor da propriedade FirstDayOfWeek do objeto cultura.</span><span class="sxs-lookup"><span data-stu-id="b991b-129">The fifth command uses dot notation to display the value of the FirstDayOfWeek property of the DateTimeFormat property.</span></span>

## <span data-ttu-id="b991b-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b991b-130">PARAMETERS</span></span>

### <span data-ttu-id="b991b-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b991b-131">CommonParameters</span></span>
<span data-ttu-id="b991b-132">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b991b-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b991b-133">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b991b-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b991b-134">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b991b-134">INPUTS</span></span>

### <span data-ttu-id="b991b-135">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b991b-135">None</span></span>
<span data-ttu-id="b991b-136">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b991b-136">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="b991b-137">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b991b-137">OUTPUTS</span></span>

### <span data-ttu-id="b991b-138">System. Globalization. CultureInfo</span><span class="sxs-lookup"><span data-stu-id="b991b-138">System.Globalization.CultureInfo</span></span>
<span data-ttu-id="b991b-139">**Get-Culture** retorna um objeto que representa a cultura atual.</span><span class="sxs-lookup"><span data-stu-id="b991b-139">**Get-Culture** returns an object that represents the current culture.</span></span>

## <span data-ttu-id="b991b-140">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b991b-140">NOTES</span></span>

* <span data-ttu-id="b991b-141">Você também pode usar as variáveis $PsCulture e $PsUICulture.</span><span class="sxs-lookup"><span data-stu-id="b991b-141">You can also use the $PsCulture and $PsUICulture variables.</span></span> <span data-ttu-id="b991b-142">A variável $PsCulture armazena o nome da cultura atual, e a variável $PsUICulture armazena o nome da cultura da interface do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="b991b-142">The $PsCulture variable stores the name of the current culture and the $PsUICulture variable stores the name of the current UI culture.</span></span>

*

## <span data-ttu-id="b991b-143">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b991b-143">RELATED LINKS</span></span>

[<span data-ttu-id="b991b-144">Set-Culture</span><span class="sxs-lookup"><span data-stu-id="b991b-144">Set-Culture</span></span>](/powershell/module/internationalcmdlets/set-culture)

[<span data-ttu-id="b991b-145">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="b991b-145">Get-UICulture</span></span>](Get-UICulture.md)
