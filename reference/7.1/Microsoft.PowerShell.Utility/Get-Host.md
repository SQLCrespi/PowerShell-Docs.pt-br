---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-host?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Host
ms.openlocfilehash: 45a7a8a44bdb116e2e7d9327fd23972cb7af1246
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "93192663"
---
# Get-Host

## SINOPSE
Obtém um objeto que representa o programa host atual.

## SYNTAX

```
Get-Host [<CommonParameters>]
```

## DESCRIPTION

O `Get-Host` cmdlet obtém um objeto que representa o programa que está hospedando o Windows PowerShell.

A exibição padrão inclui o número da versão do Windows PowerShell e a região e as configurações de idioma atuais usadas pelo host, mas o objeto de host contém uma grande quantidade de informações, inclusive informações detalhadas sobre a versão do Windows PowerShell que está sendo executada e a cultura atual e a cultura da interface do usuário do Windows PowerShell. Você também pode usar este cmdlet para personalizar os recursos da interface do usuário do programa host, como as cores de texto e de plano de fundo.

## EXEMPLOS

### Exemplo 1: obter informações sobre o host do console do PowerShell

```
PS C:\> Get-Host
Name             : ConsoleHost
Version          : 2.0
InstanceId       : e4e0ab54-cc5e-4261-9117-4081f20ce7a2
UI               : System.Management.Automation.Internal.Host.InternalHostUserInterface
CurrentCulture   : en-US
CurrentUICulture : en-US
PrivateData      : Microsoft.PowerShell.ConsoleHost+ConsoleColorProxy
IsRunspacePushed : False
Runspace         : System.Management.Automation.Runspaces.LocalRunspace
```

Este comando exibe informações sobre o console do Windows PowerShell, que é o programa host atual para o Windows PowerShell neste exemplo. Ele inclui o nome do host, a versão do Windows PowerShell que está em execução no host, a cultura atual e cultura da interface do usuário.

Cada uma das propriedades Version, UI, CurrentCulture, CurrentUICulture, PrivateData e Runspace contém um objeto com propriedades muito úteis. Exemplos posteriores examinam essas propriedades.

### Exemplo 2: redimensionar a janela do PowerShell

```powershell
PS C:\> $H = Get-Host
PS C:\> $Win = $H.UI.RawUI.WindowSize
PS C:\> $Win.Height = 10
PS C:\> $Win.Width  = 10
PS C:\> $H.UI.RawUI.Set_WindowSize($Win)
```

Este comando redimensiona a janela do Windows PowerShell para 10 pixels por 10.

### Exemplo 3: obter a versão do PowerShell para o host

```powershell
PS C:\> (Get-Host).Version | Format-List -Property *
Major         : 2
Minor         : 0
Build         : -1
Revision      : -1
MajorRevision : -1
MinorRevision : -1
```

Este comando obtém informações detalhadas sobre a versão do Windows PowerShell em execução no host.
Você pode exibir, mas não alterar, esses valores.

A Propriedade Version de `Get-Host` contém um objeto **System. Version** . Esse comando usa um operador de pipeline (|) para enviar o objeto de versão para o `Format-List` cmdlet. O `Format-List` comando usa o parâmetro *Property* com um valor de All (*) para exibir todas as propriedades e os valores de Propriedade do objeto Version.

### Exemplo 4: obter a cultura atual para o host

```powershell
PS C:\> (Get-Host).CurrentCulture | Format-List -Property *
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
```

Este comando obtém informações detalhadas sobre a cultura atual definida para o Windows PowerShell em execução no host. Essas são as mesmas informações retornadas pelo `Get-Culture` cmdlet.

Da mesma forma, a propriedade **CurrentUICulture** retorna o mesmo objeto que `Get-UICulture` retorna.

A propriedade **CurrentCulture** do objeto de host contém um objeto **System. Globalization. CultureInfo** . Esse comando usa um operador de pipeline (|) para enviar o objeto **CultureInfo** para o `Format-List` cmdlet. O `Format-List` comando usa o parâmetro *Property* com um valor de All (*) para exibir todas as propriedades e os valores de Propriedade do objeto **CultureInfo** .

### Exemplo 5: obter o DateTimeFormat para a cultura atual

```powershell
PS C:\> (Get-Host).CurrentCulture.DateTimeFormat | Format-List -Property *
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
```

Este comando retorna informações detalhadas sobre o DateTimeFormat da cultura atual que está sendo usada para o Windows PowerShell.

A propriedade **CurrentCulture** do objeto de host contém um objeto **CultureInfo** que, por sua vez, tem muitas propriedades úteis. Entre elas, a propriedade **DateTimeFormat** contém um objeto **DateTimeFormatInfo** com muitas propriedades úteis.

Para localizar o tipo de um objeto armazenado em uma propriedade de objeto, use o `Get-Member` cmdlet. Para exibir os valores de Propriedade do objeto, use o `Format-List` cmdlet.

### Exemplo 6: obter a propriedade RawUI para o host

```
PS C:\> (Get-Host).UI.RawUI | Format-List -Property *
ForegroundColor       : DarkYellow
BackgroundColor       : DarkBlue
CursorPosition        : 0,390
WindowPosition        : 0,341
CursorSize            : 25
BufferSize            : 120,3000
WindowSize            : 120,50
MaxWindowSize         : 120,81
MaxPhysicalWindowSize : 182,81
KeyAvailable          : False
WindowTitle           : Windows PowerShell 2.0 (04/11/2008 00:08:14)
```

Esse comando exibe as propriedades da propriedade **rawui** do objeto de host. Ao alterar esses valores, você pode alterar a aparência do programa host.

### Exemplo 7: definir a cor do plano de fundo para o console do PowerShell

```powershell
PS C:\> (Get-Host).UI.RawUI.BackgroundColor = "Black"
PS C:\> cls
```

Estes comandos alteram a cor de plano de fundo do console do Windows PowerShell para preto. O comando **CLS** é um alias para a `Clear-Host` função, que limpa a tela e altera a tela inteira para a nova cor.

Essa alteração entra em vigor somente na sessão atual. Para alterar a cor de plano de fundo do console de todas as sessões, adicione o comando ao seu perfil do Windows PowerShell.

### Exemplo 8: definir a cor do plano de fundo para mensagens de erro

```
PS C:\> $Host.PrivateData.ErrorBackgroundColor = "white"
```

Este comando altera a cor de plano de fundo das mensagens de erro para branco.

Esse comando usa a `$Host` variável automática, que contém o objeto de host para o programa de host atual. `Get-Host` Retorna o mesmo objeto que `$Host` contém, para que você possa usá-los de maneira intercambiável.

Esse comando usa a propriedade **PrivateData** de `$Host` como sua propriedade ErrorBackgroundColor. Para ver todas as propriedades do objeto no `$Host` . Propriedade PrivateData, digite `$host.privatedata | format-list *` .

## PARAMETERS

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum
Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### System. Management. Automation. Internal. host. InternalHost

`Get-Host` Retorna um objeto **System. Management. Automation. Internal. host. InternalHost** .

## OBSERVAÇÕES

A `$Host` variável automática contém o mesmo objeto que `Get-Host` retorna, e você pode usá-la da mesma maneira. Da mesma forma, as `$PSCulture` `$PSUICulture` variáveis e automáticas contêm os mesmos objetos que as propriedades CurrentCulture e CurrentUICulture do objeto de host contêm. Você pode usar esses recursos alternadamente.

Para obter mais informações, consulte [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).

## LINKS RELACIONADOS

[Clear-Host](../Microsoft.PowerShell.Core/Clear-Host.md)

[Read-Host](Read-Host.md)

[Write-Host](Write-Host.md)

