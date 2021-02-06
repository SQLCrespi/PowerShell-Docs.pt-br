---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-host?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Host
ms.openlocfilehash: 0775940f210cb028d7a0919bb8e5ca9f256b70d8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595556"
---
# <span data-ttu-id="c946a-102">Get-Host</span><span class="sxs-lookup"><span data-stu-id="c946a-102">Get-Host</span></span>

## <span data-ttu-id="c946a-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="c946a-103">SYNOPSIS</span></span>
<span data-ttu-id="c946a-104">Obtém um objeto que representa o programa host atual.</span><span class="sxs-lookup"><span data-stu-id="c946a-104">Gets an object that represents the current host program.</span></span>

## <span data-ttu-id="c946a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c946a-105">SYNTAX</span></span>

```
Get-Host [<CommonParameters>]
```

## <span data-ttu-id="c946a-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c946a-106">DESCRIPTION</span></span>

<span data-ttu-id="c946a-107">O `Get-Host` cmdlet obtém um objeto que representa o programa que está hospedando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c946a-107">The `Get-Host` cmdlet gets an object that represents the program that is hosting Windows PowerShell.</span></span>

<span data-ttu-id="c946a-108">A exibição padrão inclui o número da versão do Windows PowerShell e a região e as configurações de idioma atuais usadas pelo host, mas o objeto de host contém uma grande quantidade de informações, inclusive informações detalhadas sobre a versão do Windows PowerShell que está sendo executada e a cultura atual e a cultura da interface do usuário do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c946a-108">The default display includes the Windows PowerShell version number and the current region and language settings that the host is using, but the host object contains a wealth of information, including detailed information about the version of Windows PowerShell that is currently running and the current culture and UI culture of Windows PowerShell.</span></span> <span data-ttu-id="c946a-109">Você também pode usar este cmdlet para personalizar os recursos da interface do usuário do programa host, como as cores de texto e de plano de fundo.</span><span class="sxs-lookup"><span data-stu-id="c946a-109">You can also use this cmdlet to customize features of the host program user interface, such as the text and background colors.</span></span>

## <span data-ttu-id="c946a-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="c946a-110">EXAMPLES</span></span>

### <span data-ttu-id="c946a-111">Exemplo 1: obter informações sobre o host do console do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c946a-111">Example 1: Get information about the PowerShell console host</span></span>

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

<span data-ttu-id="c946a-112">Este comando exibe informações sobre o console do Windows PowerShell, que é o programa host atual para o Windows PowerShell neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="c946a-112">This command displays information about the Windows PowerShell console, which is the current host program for Windows PowerShell in this example.</span></span> <span data-ttu-id="c946a-113">Ele inclui o nome do host, a versão do Windows PowerShell que está em execução no host, a cultura atual e cultura da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="c946a-113">It includes the name of the host, the version of Windows PowerShell that is running in the host, and current culture and UI culture.</span></span>

<span data-ttu-id="c946a-114">Cada uma das propriedades Version, UI, CurrentCulture, CurrentUICulture, PrivateData e Runspace contém um objeto com propriedades muito úteis.</span><span class="sxs-lookup"><span data-stu-id="c946a-114">The Version, UI, CurrentCulture, CurrentUICulture, PrivateData, and Runspace properties each contain an object with very useful properties.</span></span> <span data-ttu-id="c946a-115">Exemplos posteriores examinam essas propriedades.</span><span class="sxs-lookup"><span data-stu-id="c946a-115">Later examples examine these properties.</span></span>

### <span data-ttu-id="c946a-116">Exemplo 2: redimensionar a janela do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c946a-116">Example 2: Resize the PowerShell window</span></span>

```powershell
PS C:\> $H = Get-Host
PS C:\> $Win = $H.UI.RawUI.WindowSize
PS C:\> $Win.Height = 10
PS C:\> $Win.Width  = 10
PS C:\> $H.UI.RawUI.Set_WindowSize($Win)
```

<span data-ttu-id="c946a-117">Este comando redimensiona a janela do Windows PowerShell para 10 pixels por 10.</span><span class="sxs-lookup"><span data-stu-id="c946a-117">This command resizes the Windows PowerShell window to 10 pixels by 10 pixels.</span></span>

### <span data-ttu-id="c946a-118">Exemplo 3: obter a versão do PowerShell para o host</span><span class="sxs-lookup"><span data-stu-id="c946a-118">Example 3: Get the PowerShell version for the host</span></span>

```powershell
PS C:\> (Get-Host).Version | Format-List -Property *
Major         : 2
Minor         : 0
Build         : -1
Revision      : -1
MajorRevision : -1
MinorRevision : -1
```

<span data-ttu-id="c946a-119">Este comando obtém informações detalhadas sobre a versão do Windows PowerShell em execução no host.</span><span class="sxs-lookup"><span data-stu-id="c946a-119">This command gets detailed information about the version of Windows PowerShell running in the host.</span></span>
<span data-ttu-id="c946a-120">Você pode exibir, mas não alterar, esses valores.</span><span class="sxs-lookup"><span data-stu-id="c946a-120">You can view, but not change, these values.</span></span>

<span data-ttu-id="c946a-121">A Propriedade Version de `Get-Host` contém um objeto **System. Version** .</span><span class="sxs-lookup"><span data-stu-id="c946a-121">The Version property of `Get-Host` contains a **System.Version** object.</span></span> <span data-ttu-id="c946a-122">Esse comando usa um operador de pipeline (|) para enviar o objeto de versão para o `Format-List` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c946a-122">This command uses a pipeline operator (|) to send the version object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="c946a-123">O `Format-List` comando usa o parâmetro *Property* com um valor de All (\*) para exibir todas as propriedades e os valores de Propriedade do objeto Version.</span><span class="sxs-lookup"><span data-stu-id="c946a-123">The `Format-List` command uses the *Property* parameter with a value of all (\*) to display all of the properties and property values of the version object.</span></span>

### <span data-ttu-id="c946a-124">Exemplo 4: obter a cultura atual para o host</span><span class="sxs-lookup"><span data-stu-id="c946a-124">Example 4: Get the current culture for the host</span></span>

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

<span data-ttu-id="c946a-125">Este comando obtém informações detalhadas sobre a cultura atual definida para o Windows PowerShell em execução no host.</span><span class="sxs-lookup"><span data-stu-id="c946a-125">This command gets detailed information about the current culture set for Windows PowerShell running in the host.</span></span> <span data-ttu-id="c946a-126">Essas são as mesmas informações retornadas pelo `Get-Culture` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c946a-126">This is the same information that is returned by the `Get-Culture` cmdlet.</span></span>

<span data-ttu-id="c946a-127">Da mesma forma, a propriedade **CurrentUICulture** retorna o mesmo objeto que `Get-UICulture` retorna.</span><span class="sxs-lookup"><span data-stu-id="c946a-127">Similarly, the **CurrentUICulture** property returns the same object that `Get-UICulture` returns.</span></span>

<span data-ttu-id="c946a-128">A propriedade **CurrentCulture** do objeto de host contém um objeto **System. Globalization. CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="c946a-128">The **CurrentCulture** property of the host object contains a **System.Globalization.CultureInfo** object.</span></span> <span data-ttu-id="c946a-129">Esse comando usa um operador de pipeline (|) para enviar o objeto **CultureInfo** para o `Format-List` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c946a-129">This command uses a pipeline operator (|) to send the **CultureInfo** object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="c946a-130">O `Format-List` comando usa o parâmetro *Property* com um valor de All (\*) para exibir todas as propriedades e os valores de Propriedade do objeto **CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="c946a-130">The `Format-List` command uses the *Property* parameter with a value of all (\*) to display all of the properties and property values of the **CultureInfo** object.</span></span>

### <span data-ttu-id="c946a-131">Exemplo 5: obter o DateTimeFormat para a cultura atual</span><span class="sxs-lookup"><span data-stu-id="c946a-131">Example 5: Get the DateTimeFormat for the current culture</span></span>

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

<span data-ttu-id="c946a-132">Este comando retorna informações detalhadas sobre o DateTimeFormat da cultura atual que está sendo usada para o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c946a-132">This command returns detailed information about the DateTimeFormat of the current culture that is being used for Windows PowerShell.</span></span>

<span data-ttu-id="c946a-133">A propriedade **CurrentCulture** do objeto de host contém um objeto **CultureInfo** que, por sua vez, tem muitas propriedades úteis.</span><span class="sxs-lookup"><span data-stu-id="c946a-133">The **CurrentCulture** property of the host object contains a **CultureInfo** object that, in turn, has many useful properties.</span></span> <span data-ttu-id="c946a-134">Entre elas, a propriedade **DateTimeFormat** contém um objeto **DateTimeFormatInfo** com muitas propriedades úteis.</span><span class="sxs-lookup"><span data-stu-id="c946a-134">Among them, the **DateTimeFormat** property contains a **DateTimeFormatInfo** object with many useful properties.</span></span>

<span data-ttu-id="c946a-135">Para localizar o tipo de um objeto armazenado em uma propriedade de objeto, use o `Get-Member` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c946a-135">To find the type of an object that is stored in an object property, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="c946a-136">Para exibir os valores de Propriedade do objeto, use o `Format-List` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c946a-136">To display the property values of the object, use the `Format-List` cmdlet.</span></span>

### <span data-ttu-id="c946a-137">Exemplo 6: obter a propriedade RawUI para o host</span><span class="sxs-lookup"><span data-stu-id="c946a-137">Example 6: Get the RawUI property for the host</span></span>

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

<span data-ttu-id="c946a-138">Esse comando exibe as propriedades da propriedade **rawui** do objeto de host.</span><span class="sxs-lookup"><span data-stu-id="c946a-138">This command displays the properties of the **RawUI** property of the host object.</span></span> <span data-ttu-id="c946a-139">Ao alterar esses valores, você pode alterar a aparência do programa host.</span><span class="sxs-lookup"><span data-stu-id="c946a-139">By changing these values, you can change the appearance of the host program.</span></span>

### <span data-ttu-id="c946a-140">Exemplo 7: definir a cor do plano de fundo para o console do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c946a-140">Example 7: Set the background color for the PowerShell console</span></span>

```powershell
PS C:\> (Get-Host).UI.RawUI.BackgroundColor = "Black"
PS C:\> cls
```

<span data-ttu-id="c946a-141">Estes comandos alteram a cor de plano de fundo do console do Windows PowerShell para preto.</span><span class="sxs-lookup"><span data-stu-id="c946a-141">These commands change the background color of the Windows PowerShell console to black.</span></span> <span data-ttu-id="c946a-142">O comando **CLS** é um alias para a `Clear-Host` função, que limpa a tela e altera a tela inteira para a nova cor.</span><span class="sxs-lookup"><span data-stu-id="c946a-142">The **cls** command is an alias for the `Clear-Host` function, which clears the screen and changes the whole screen to the new color.</span></span>

<span data-ttu-id="c946a-143">Essa alteração entra em vigor somente na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="c946a-143">This change is effective only in the current session.</span></span> <span data-ttu-id="c946a-144">Para alterar a cor de plano de fundo do console de todas as sessões, adicione o comando ao seu perfil do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c946a-144">To change the background color of the console for all sessions, add the command to your Windows PowerShell profile.</span></span>

### <span data-ttu-id="c946a-145">Exemplo 8: definir a cor do plano de fundo para mensagens de erro</span><span class="sxs-lookup"><span data-stu-id="c946a-145">Example 8: Set the background color for error messages</span></span>

```
PS C:\> $Host.PrivateData.ErrorBackgroundColor = "white"
```

<span data-ttu-id="c946a-146">Este comando altera a cor de plano de fundo das mensagens de erro para branco.</span><span class="sxs-lookup"><span data-stu-id="c946a-146">This command changes the background color of error messages to white.</span></span>

<span data-ttu-id="c946a-147">Esse comando usa a `$Host` variável automática, que contém o objeto de host para o programa de host atual.</span><span class="sxs-lookup"><span data-stu-id="c946a-147">This command uses the `$Host` automatic variable, which contains the host object for the current host program.</span></span> <span data-ttu-id="c946a-148">`Get-Host` Retorna o mesmo objeto que `$Host` contém, para que você possa usá-los de maneira intercambiável.</span><span class="sxs-lookup"><span data-stu-id="c946a-148">`Get-Host` returns the same object that `$Host` contains, so you can use them interchangeably.</span></span>

<span data-ttu-id="c946a-149">Esse comando usa a propriedade **PrivateData** de `$Host` como sua propriedade ErrorBackgroundColor.</span><span class="sxs-lookup"><span data-stu-id="c946a-149">This command uses the **PrivateData** property of `$Host` as its ErrorBackgroundColor property.</span></span> <span data-ttu-id="c946a-150">Para ver todas as propriedades do objeto no `$Host` . Propriedade PrivateData, digite `$host.privatedata | format-list *` .</span><span class="sxs-lookup"><span data-stu-id="c946a-150">To see all of the properties of the object in the `$Host`.PrivateData property, type `$host.privatedata | format-list *`.</span></span>

## <span data-ttu-id="c946a-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c946a-151">PARAMETERS</span></span>

### <span data-ttu-id="c946a-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c946a-152">CommonParameters</span></span>

<span data-ttu-id="c946a-153">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c946a-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c946a-154">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c946a-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c946a-155">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="c946a-155">INPUTS</span></span>

### <span data-ttu-id="c946a-156">Nenhum</span><span class="sxs-lookup"><span data-stu-id="c946a-156">None</span></span>
<span data-ttu-id="c946a-157">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c946a-157">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="c946a-158">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="c946a-158">OUTPUTS</span></span>

### <span data-ttu-id="c946a-159">System. Management. Automation. Internal. host. InternalHost</span><span class="sxs-lookup"><span data-stu-id="c946a-159">System.Management.Automation.Internal.Host.InternalHost</span></span>

<span data-ttu-id="c946a-160">`Get-Host` Retorna um objeto **System. Management. Automation. Internal. host. InternalHost** .</span><span class="sxs-lookup"><span data-stu-id="c946a-160">`Get-Host` returns a **System.Management.Automation.Internal.Host.InternalHost** object.</span></span>

## <span data-ttu-id="c946a-161">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="c946a-161">NOTES</span></span>

<span data-ttu-id="c946a-162">A `$Host` variável automática contém o mesmo objeto que `Get-Host` retorna, e você pode usá-la da mesma maneira.</span><span class="sxs-lookup"><span data-stu-id="c946a-162">The `$Host` automatic variable contains the same object that `Get-Host` returns, and you can use it in the same way.</span></span> <span data-ttu-id="c946a-163">Da mesma forma, as `$PSCulture` `$PSUICulture` variáveis e automáticas contêm os mesmos objetos que as propriedades CurrentCulture e CurrentUICulture do objeto de host contêm.</span><span class="sxs-lookup"><span data-stu-id="c946a-163">Similarly, the `$PSCulture` and `$PSUICulture` automatic variables contain the same objects that the CurrentCulture and CurrentUICulture properties of the host object contain.</span></span> <span data-ttu-id="c946a-164">Você pode usar esses recursos alternadamente.</span><span class="sxs-lookup"><span data-stu-id="c946a-164">You can use these features interchangeably.</span></span>

<span data-ttu-id="c946a-165">Para obter mais informações, consulte [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="c946a-165">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

## <span data-ttu-id="c946a-166">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="c946a-166">RELATED LINKS</span></span>

[<span data-ttu-id="c946a-167">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="c946a-167">Clear-Host</span></span>](../Microsoft.PowerShell.Core/Clear-Host.md)

[<span data-ttu-id="c946a-168">Read-Host</span><span class="sxs-lookup"><span data-stu-id="c946a-168">Read-Host</span></span>](Read-Host.md)

[<span data-ttu-id="c946a-169">Write-Host</span><span class="sxs-lookup"><span data-stu-id="c946a-169">Write-Host</span></span>](Write-Host.md)

