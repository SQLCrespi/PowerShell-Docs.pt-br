---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/22/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-host?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Host
ms.openlocfilehash: da48cdaf11a7dd0f1d8a169ca145fecc5052bf02
ms.sourcegitcommit: a0148ef8bf9757f68c788d24f2eaf92792c3979f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2021
ms.locfileid: "104796253"
---
# <span data-ttu-id="9fec4-102">Get-Host</span><span class="sxs-lookup"><span data-stu-id="9fec4-102">Get-Host</span></span>

## <span data-ttu-id="9fec4-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="9fec4-103">SYNOPSIS</span></span>
<span data-ttu-id="9fec4-104">Obtém um objeto que representa o programa host atual.</span><span class="sxs-lookup"><span data-stu-id="9fec4-104">Gets an object that represents the current host program.</span></span>

## <span data-ttu-id="9fec4-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9fec4-105">SYNTAX</span></span>

```
Get-Host [<CommonParameters>]
```

## <span data-ttu-id="9fec4-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9fec4-106">DESCRIPTION</span></span>

<span data-ttu-id="9fec4-107">O `Get-Host` cmdlet obtém um objeto que representa o programa que está hospedando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fec4-107">The `Get-Host` cmdlet gets an object that represents the program that is hosting Windows PowerShell.</span></span>

<span data-ttu-id="9fec4-108">A exibição padrão inclui o número da versão do Windows PowerShell e a região e as configurações de idioma atuais usadas pelo host, mas o objeto de host contém uma grande quantidade de informações, inclusive informações detalhadas sobre a versão do Windows PowerShell que está sendo executada e a cultura atual e a cultura da interface do usuário do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fec4-108">The default display includes the Windows PowerShell version number and the current region and language settings that the host is using, but the host object contains a wealth of information, including detailed information about the version of Windows PowerShell that is currently running and the current culture and UI culture of Windows PowerShell.</span></span> <span data-ttu-id="9fec4-109">Você também pode usar este cmdlet para personalizar os recursos da interface do usuário do programa host, como as cores de texto e de plano de fundo.</span><span class="sxs-lookup"><span data-stu-id="9fec4-109">You can also use this cmdlet to customize features of the host program user interface, such as the text and background colors.</span></span>

## <span data-ttu-id="9fec4-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="9fec4-110">EXAMPLES</span></span>

### <span data-ttu-id="9fec4-111">Exemplo 1: obter informações sobre o host do console do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9fec4-111">Example 1: Get information about the PowerShell console host</span></span>

```
Get-Host

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

<span data-ttu-id="9fec4-112">Este comando exibe informações sobre o console do PowerShell, que é o programa de host atual para o PowerShell neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="9fec4-112">This command displays information about the PowerShell console, which is the current host program for PowerShell in this example.</span></span> <span data-ttu-id="9fec4-113">Ele inclui o nome do host, a versão do PowerShell que está sendo executada no host e a cultura atual e a cultura da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="9fec4-113">It includes the name of the host, the version of PowerShell that is running in the host, and current culture and UI culture.</span></span>

<span data-ttu-id="9fec4-114">A **versão**, a **interface do usuário**, **CurrentCulture**, **CurrentUICulture**, **PrivateData** e as propriedades de **runspace** contêm um objeto com outras propriedades úteis.</span><span class="sxs-lookup"><span data-stu-id="9fec4-114">The **Version**, **UI**, **CurrentCulture**, **CurrentUICulture**, **PrivateData**, and **Runspace** properties each contain an object with other useful properties.</span></span> <span data-ttu-id="9fec4-115">Exemplos posteriores examinam essas propriedades.</span><span class="sxs-lookup"><span data-stu-id="9fec4-115">Later examples examine these properties.</span></span>

### <span data-ttu-id="9fec4-116">Exemplo 2: redimensionar a janela do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9fec4-116">Example 2: Resize the PowerShell window</span></span>

```powershell
$H = Get-Host
$Win = $H.UI.RawUI.WindowSize
$Win.Height = 10
$Win.Width  = 10
$H.UI.RawUI.Set_WindowSize($Win)
```

<span data-ttu-id="9fec4-117">Esse comando redimensiona a janela do Windows PowerShell para 10 linhas por 10 caracteres.</span><span class="sxs-lookup"><span data-stu-id="9fec4-117">This command resizes the Windows PowerShell window to 10 lines by 10 characters.</span></span>

### <span data-ttu-id="9fec4-118">Exemplo 3: obter a versão do PowerShell para o host</span><span class="sxs-lookup"><span data-stu-id="9fec4-118">Example 3: Get the PowerShell version for the host</span></span>

```powershell
(Get-Host).Version | Format-List -Property *

Major         : 2
Minor         : 0
Build         : -1
Revision      : -1
MajorRevision : -1
MinorRevision : -1
```

<span data-ttu-id="9fec4-119">Este comando obtém informações detalhadas sobre a versão do Windows PowerShell em execução no host.</span><span class="sxs-lookup"><span data-stu-id="9fec4-119">This command gets detailed information about the version of Windows PowerShell running in the host.</span></span>
<span data-ttu-id="9fec4-120">Você pode exibir, mas não alterar, esses valores.</span><span class="sxs-lookup"><span data-stu-id="9fec4-120">You can view, but not change, these values.</span></span>

<span data-ttu-id="9fec4-121">A Propriedade Version de `Get-Host` contém um objeto **System. Version** .</span><span class="sxs-lookup"><span data-stu-id="9fec4-121">The Version property of `Get-Host` contains a **System.Version** object.</span></span> <span data-ttu-id="9fec4-122">Esse comando usa um operador de pipeline ( `|` ) para enviar o objeto de versão para o `Format-List` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9fec4-122">This command uses a pipeline operator (`|`) to send the version object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="9fec4-123">O `Format-List` comando usa o parâmetro **Property** com um valor de All ( `*` ) para exibir todas as propriedades e os valores de Propriedade do objeto Version.</span><span class="sxs-lookup"><span data-stu-id="9fec4-123">The `Format-List` command uses the **Property** parameter with a value of all (`*`) to display all of the properties and property values of the version object.</span></span>

### <span data-ttu-id="9fec4-124">Exemplo 4: obter a cultura atual para o host</span><span class="sxs-lookup"><span data-stu-id="9fec4-124">Example 4: Get the current culture for the host</span></span>

```powershell
(Get-Host).CurrentCulture | Format-List -Property *

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

<span data-ttu-id="9fec4-125">Este comando obtém informações detalhadas sobre a cultura atual definida para o Windows PowerShell em execução no host.</span><span class="sxs-lookup"><span data-stu-id="9fec4-125">This command gets detailed information about the current culture set for Windows PowerShell running in the host.</span></span> <span data-ttu-id="9fec4-126">Essas são as mesmas informações retornadas pelo `Get-Culture` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9fec4-126">This is the same information that is returned by the `Get-Culture` cmdlet.</span></span>

<span data-ttu-id="9fec4-127">Da mesma forma, a propriedade **CurrentUICulture** retorna o mesmo objeto que `Get-UICulture` retorna.</span><span class="sxs-lookup"><span data-stu-id="9fec4-127">Similarly, the **CurrentUICulture** property returns the same object that `Get-UICulture` returns.</span></span>

<span data-ttu-id="9fec4-128">A propriedade **CurrentCulture** do objeto de host contém um objeto **System. Globalization. CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="9fec4-128">The **CurrentCulture** property of the host object contains a **System.Globalization.CultureInfo** object.</span></span> <span data-ttu-id="9fec4-129">Esse comando usa um operador de pipeline ( `|` ) para enviar o objeto **CultureInfo** para o `Format-List` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9fec4-129">This command uses a pipeline operator (`|`) to send the **CultureInfo** object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="9fec4-130">O `Format-List` comando usa o parâmetro **Property** com um valor de All ( `*` ) para exibir todas as propriedades e os valores de Propriedade do objeto **CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="9fec4-130">The `Format-List` command uses the **Property** parameter with a value of all (`*`) to display all of the properties and property values of the **CultureInfo** object.</span></span>

### <span data-ttu-id="9fec4-131">Exemplo 5: obter o DateTimeFormat para a cultura atual</span><span class="sxs-lookup"><span data-stu-id="9fec4-131">Example 5: Get the DateTimeFormat for the current culture</span></span>

```powershell
(Get-Host).CurrentCulture.DateTimeFormat | Format-List -Property *

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

<span data-ttu-id="9fec4-132">Este comando retorna informações detalhadas sobre o DateTimeFormat da cultura atual que está sendo usada para o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fec4-132">This command returns detailed information about the DateTimeFormat of the current culture that is being used for Windows PowerShell.</span></span>

<span data-ttu-id="9fec4-133">A propriedade **CurrentCulture** do objeto de host contém um objeto **CultureInfo** que, por sua vez, tem muitas propriedades úteis.</span><span class="sxs-lookup"><span data-stu-id="9fec4-133">The **CurrentCulture** property of the host object contains a **CultureInfo** object that, in turn, has many useful properties.</span></span> <span data-ttu-id="9fec4-134">Entre elas, a propriedade **DateTimeFormat** contém um objeto **DateTimeFormatInfo** com muitas propriedades úteis.</span><span class="sxs-lookup"><span data-stu-id="9fec4-134">Among them, the **DateTimeFormat** property contains a **DateTimeFormatInfo** object with many useful properties.</span></span>

<span data-ttu-id="9fec4-135">Para localizar o tipo de um objeto armazenado em uma propriedade de objeto, use o `Get-Member` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9fec4-135">To find the type of an object that is stored in an object property, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="9fec4-136">Para exibir os valores de Propriedade do objeto, use o `Format-List` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9fec4-136">To display the property values of the object, use the `Format-List` cmdlet.</span></span>

### <span data-ttu-id="9fec4-137">Exemplo 6: obter a propriedade RawUI para o host</span><span class="sxs-lookup"><span data-stu-id="9fec4-137">Example 6: Get the RawUI property for the host</span></span>

```
(Get-Host).UI.RawUI | Format-List -Property *

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

<span data-ttu-id="9fec4-138">Esse comando exibe as propriedades da propriedade **rawui** do objeto de host.</span><span class="sxs-lookup"><span data-stu-id="9fec4-138">This command displays the properties of the **RawUI** property of the host object.</span></span> <span data-ttu-id="9fec4-139">Ao alterar esses valores, você pode alterar a aparência do programa host.</span><span class="sxs-lookup"><span data-stu-id="9fec4-139">By changing these values, you can change the appearance of the host program.</span></span>

### <span data-ttu-id="9fec4-140">Exemplo 7: definir a cor do plano de fundo para o console do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9fec4-140">Example 7: Set the background color for the PowerShell console</span></span>

```powershell
(Get-Host).UI.RawUI.BackgroundColor = "Black"
cls
```

<span data-ttu-id="9fec4-141">Estes comandos alteram a cor de plano de fundo do console do Windows PowerShell para preto.</span><span class="sxs-lookup"><span data-stu-id="9fec4-141">These commands change the background color of the Windows PowerShell console to black.</span></span> <span data-ttu-id="9fec4-142">O comando **CLS** é um alias para a `Clear-Host` função, que limpa a tela e altera a tela inteira para a nova cor.</span><span class="sxs-lookup"><span data-stu-id="9fec4-142">The **cls** command is an alias for the `Clear-Host` function, which clears the screen and changes the whole screen to the new color.</span></span>

<span data-ttu-id="9fec4-143">Essa alteração entra em vigor somente na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="9fec4-143">This change is effective only in the current session.</span></span> <span data-ttu-id="9fec4-144">Para alterar a cor do plano de fundo do console para todas as sessões, adicione o comando ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fec4-144">To change the background color of the console for all sessions, add the command to your PowerShell profile.</span></span>

### <span data-ttu-id="9fec4-145">Exemplo 8: definir a cor do plano de fundo para mensagens de erro</span><span class="sxs-lookup"><span data-stu-id="9fec4-145">Example 8: Set the background color for error messages</span></span>

```powershell
$Host.PrivateData.ErrorBackgroundColor = "white"
```

<span data-ttu-id="9fec4-146">Este comando altera a cor de plano de fundo das mensagens de erro para branco.</span><span class="sxs-lookup"><span data-stu-id="9fec4-146">This command changes the background color of error messages to white.</span></span>

<span data-ttu-id="9fec4-147">Esse comando usa a `$Host` variável automática, que contém o objeto de host para o programa de host atual.</span><span class="sxs-lookup"><span data-stu-id="9fec4-147">This command uses the `$Host` automatic variable, which contains the host object for the current host program.</span></span> <span data-ttu-id="9fec4-148">`Get-Host` Retorna o mesmo objeto que `$Host` contém, para que você possa usá-los de maneira intercambiável.</span><span class="sxs-lookup"><span data-stu-id="9fec4-148">`Get-Host` returns the same object that `$Host` contains, so you can use them interchangeably.</span></span>

<span data-ttu-id="9fec4-149">Esse comando usa a propriedade **PrivateData** de `$Host` como sua propriedade ErrorBackgroundColor.</span><span class="sxs-lookup"><span data-stu-id="9fec4-149">This command uses the **PrivateData** property of `$Host` as its ErrorBackgroundColor property.</span></span> <span data-ttu-id="9fec4-150">Para ver todas as propriedades do objeto no `$Host` . Propriedade PrivateData, digite `$host.PrivateData | format-list *` .</span><span class="sxs-lookup"><span data-stu-id="9fec4-150">To see all of the properties of the object in the `$Host`.PrivateData property, type `$host.PrivateData | format-list *`.</span></span>

## <span data-ttu-id="9fec4-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9fec4-151">PARAMETERS</span></span>

### <span data-ttu-id="9fec4-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9fec4-152">CommonParameters</span></span>

<span data-ttu-id="9fec4-153">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9fec4-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9fec4-154">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9fec4-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9fec4-155">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="9fec4-155">INPUTS</span></span>

### <span data-ttu-id="9fec4-156">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9fec4-156">None</span></span>

<span data-ttu-id="9fec4-157">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9fec4-157">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="9fec4-158">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="9fec4-158">OUTPUTS</span></span>

### <span data-ttu-id="9fec4-159">System. Management. Automation. Internal. host. InternalHost</span><span class="sxs-lookup"><span data-stu-id="9fec4-159">System.Management.Automation.Internal.Host.InternalHost</span></span>

<span data-ttu-id="9fec4-160">`Get-Host` Retorna um objeto **System. Management. Automation. Internal. host. InternalHost** .</span><span class="sxs-lookup"><span data-stu-id="9fec4-160">`Get-Host` returns a **System.Management.Automation.Internal.Host.InternalHost** object.</span></span>

## <span data-ttu-id="9fec4-161">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="9fec4-161">NOTES</span></span>

<span data-ttu-id="9fec4-162">A `$Host` variável automática contém o mesmo objeto que `Get-Host` retorna, e você pode usá-la da mesma maneira.</span><span class="sxs-lookup"><span data-stu-id="9fec4-162">The `$Host` automatic variable contains the same object that `Get-Host` returns, and you can use it in the same way.</span></span> <span data-ttu-id="9fec4-163">Da mesma forma, as `$PSCulture` `$PSUICulture` variáveis e automáticas contêm os mesmos objetos que as propriedades CurrentCulture e CurrentUICulture do objeto de host contêm.</span><span class="sxs-lookup"><span data-stu-id="9fec4-163">Similarly, the `$PSCulture` and `$PSUICulture` automatic variables contain the same objects that the CurrentCulture and CurrentUICulture properties of the host object contain.</span></span> <span data-ttu-id="9fec4-164">Você pode usar esses recursos alternadamente.</span><span class="sxs-lookup"><span data-stu-id="9fec4-164">You can use these features interchangeably.</span></span>

<span data-ttu-id="9fec4-165">Para obter mais informações, consulte [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="9fec4-165">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

## <span data-ttu-id="9fec4-166">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="9fec4-166">RELATED LINKS</span></span>

[<span data-ttu-id="9fec4-167">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="9fec4-167">Clear-Host</span></span>](../Microsoft.PowerShell.Core/Clear-Host.md)

[<span data-ttu-id="9fec4-168">Read-Host</span><span class="sxs-lookup"><span data-stu-id="9fec4-168">Read-Host</span></span>](Read-Host.md)

[<span data-ttu-id="9fec4-169">Write-Host</span><span class="sxs-lookup"><span data-stu-id="9fec4-169">Write-Host</span></span>](Write-Host.md)
