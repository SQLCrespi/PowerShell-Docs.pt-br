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
# Get-Culture

## SINOPSE
Obtém a cultura atual definida no sistema operacional.

## SYNTAX

```
Get-Culture [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Get-Culture** Obtém informações sobre as configurações de cultura atuais.
Isso inclui informações sobre as configurações de idioma atuais no sistema, como o layout do teclado e o formato de exibição de itens como números, moeda e datas.

Você também pode usar o cmdlet Get-UICulture, que obtém a cultura da interface do usuário atual no sistema e o cmdlet [set-Culture](https://go.microsoft.com/fwlink/?LinkID=242258) no módulo internacional.
A cultura da interface do usuário determina quais cadeias de caracteres de texto serão usadas para elementos de interface do usuário, como menus e mensagens.

## EXEMPLOS

### Exemplo 1: obter configurações de cultura

```
PS C:\> Get-Culture
```

Este comando exibe informações sobre as configurações regionais do computador.

### Exemplo 2: Formatar as propriedades de um objeto de cultura

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

Este exemplo demonstra a enorme quantidade de dados do objeto de cultura.
Ele mostra como exibir as propriedades e subpropriedades do objeto.

O primeiro comando usa o cmdlet **Get-Culture** para obter as configurações de cultura atuais no computador.
Ele armazena o objeto de cultura resultante na variável $C.

O segundo comando exibe todas as propriedades do objeto de cultura.
Ele usa um operador de pipeline (|) para enviar o objeto de cultura em $C para o cmdlet Format-List.
Ele usa o parâmetro *Property* para exibir todas as propriedades (*) do objeto.
Esse comando pode ser abreviado como `$c | fl *` .

Os comandos restantes exploram as propriedades do objeto cultura usando a notação de ponto para exibir os valores das propriedades do objeto.
Você pode usar essa notação para exibir o valor de qualquer propriedade do objeto.

O terceiro comando usa a notação de ponto para exibir o valor da propriedade Calendar do objeto cultura.

O quarto comando usa a notação de ponto para exibir o valor da propriedade DataTimeFormat do objeto cultura.

Muitas propriedades de objeto têm propriedades.
O quinto comando usa a notação de ponto para exibir o valor da propriedade FirstDayOfWeek do objeto cultura.

## PARAMETERS

### CommonParameters
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum
Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### System. Globalization. CultureInfo
**Get-Culture** retorna um objeto que representa a cultura atual.

## OBSERVAÇÕES

* Você também pode usar as variáveis $PsCulture e $PsUICulture. A variável $PsCulture armazena o nome da cultura atual, e a variável $PsUICulture armazena o nome da cultura da interface do usuário atual.

*

## LINKS RELACIONADOS

[Set-Culture](/powershell/module/internationalcmdlets/set-culture)

[Get-UICulture](Get-UICulture.md)
