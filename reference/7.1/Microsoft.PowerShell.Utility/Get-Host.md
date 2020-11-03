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
# <span data-ttu-id="e2649-103">Get-Host</span><span class="sxs-lookup"><span data-stu-id="e2649-103">Get-Host</span></span>

## <span data-ttu-id="e2649-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="e2649-104">SYNOPSIS</span></span>
<span data-ttu-id="e2649-105">Obtém um objeto que representa o programa host atual.</span><span class="sxs-lookup"><span data-stu-id="e2649-105">Gets an object that represents the current host program.</span></span>

## <span data-ttu-id="e2649-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e2649-106">SYNTAX</span></span>

```
Get-Host [<CommonParameters>]
```

## <span data-ttu-id="e2649-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e2649-107">DESCRIPTION</span></span>

<span data-ttu-id="e2649-108">O `Get-Host` cmdlet obtém um objeto que representa o programa que está hospedando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2649-108">The `Get-Host` cmdlet gets an object that represents the program that is hosting Windows PowerShell.</span></span>

<span data-ttu-id="e2649-109">A exibição padrão inclui o número da versão do Windows PowerShell e a região e as configurações de idioma atuais usadas pelo host, mas o objeto de host contém uma grande quantidade de informações, inclusive informações detalhadas sobre a versão do Windows PowerShell que está sendo executada e a cultura atual e a cultura da interface do usuário do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2649-109">The default display includes the Windows PowerShell version number and the current region and language settings that the host is using, but the host object contains a wealth of information, including detailed information about the version of Windows PowerShell that is currently running and the current culture and UI culture of Windows PowerShell.</span></span> <span data-ttu-id="e2649-110">Você também pode usar este cmdlet para personalizar os recursos da interface do usuário do programa host, como as cores de texto e de plano de fundo.</span><span class="sxs-lookup"><span data-stu-id="e2649-110">You can also use this cmdlet to customize features of the host program user interface, such as the text and background colors.</span></span>

## <span data-ttu-id="e2649-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e2649-111">EXAMPLES</span></span>

### <span data-ttu-id="e2649-112">Exemplo 1: obter informações sobre o host do console do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2649-112">Example 1: Get information about the PowerShell console host</span></span>

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

<span data-ttu-id="e2649-113">Este comando exibe informações sobre o console do Windows PowerShell, que é o programa host atual para o Windows PowerShell neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="e2649-113">This command displays information about the Windows PowerShell console, which is the current host program for Windows PowerShell in this example.</span></span> <span data-ttu-id="e2649-114">Ele inclui o nome do host, a versão do Windows PowerShell que está em execução no host, a cultura atual e cultura da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="e2649-114">It includes the name of the host, the version of Windows PowerShell that is running in the host, and current culture and UI culture.</span></span>

<span data-ttu-id="e2649-115">Cada uma das propriedades Version, UI, CurrentCulture, CurrentUICulture, PrivateData e Runspace contém um objeto com propriedades muito úteis.</span><span class="sxs-lookup"><span data-stu-id="e2649-115">The Version, UI, CurrentCulture, CurrentUICulture, PrivateData, and Runspace properties each contain an object with very useful properties.</span></span> <span data-ttu-id="e2649-116">Exemplos posteriores examinam essas propriedades.</span><span class="sxs-lookup"><span data-stu-id="e2649-116">Later examples examine these properties.</span></span>

### <span data-ttu-id="e2649-117">Exemplo 2: redimensionar a janela do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2649-117">Example 2: Resize the PowerShell window</span></span>

```powershell
PS C:\> $H = Get-Host
PS C:\> $Win = $H.UI.RawUI.WindowSize
PS C:\> $Win.Height = 10
PS C:\> $Win.Width  = 10
PS C:\> $H.UI.RawUI.Set_WindowSize($Win)
```

<span data-ttu-id="e2649-118">Este comando redimensiona a janela do Windows PowerShell para 10 pixels por 10.</span><span class="sxs-lookup"><span data-stu-id="e2649-118">This command resizes the Windows PowerShell window to 10 pixels by 10 pixels.</span></span>

### <span data-ttu-id="e2649-119">Exemplo 3: obter a versão do PowerShell para o host</span><span class="sxs-lookup"><span data-stu-id="e2649-119">Example 3: Get the PowerShell version for the host</span></span>

```powershell
PS C:\> (Get-Host).Version | Format-List -Property *
Major         : 2
Minor         : 0
Build         : -1
Revision      : -1
MajorRevision : -1
MinorRevision : -1
```

<span data-ttu-id="e2649-120">Este comando obtém informações detalhadas sobre a versão do Windows PowerShell em execução no host.</span><span class="sxs-lookup"><span data-stu-id="e2649-120">This command gets detailed information about the version of Windows PowerShell running in the host.</span></span>
<span data-ttu-id="e2649-121">Você pode exibir, mas não alterar, esses valores.</span><span class="sxs-lookup"><span data-stu-id="e2649-121">You can view, but not change, these values.</span></span>

<span data-ttu-id="e2649-122">A Propriedade Version de `Get-Host` contém um objeto **System. Version** .</span><span class="sxs-lookup"><span data-stu-id="e2649-122">The Version property of `Get-Host` contains a **System.Version** object.</span></span> <span data-ttu-id="e2649-123">Esse comando usa um operador de pipeline (|) para enviar o objeto de versão para o `Format-List` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e2649-123">This command uses a pipeline operator (|) to send the version object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="e2649-124">O `Format-List` comando usa o parâmetro *Property* com um valor de All (\*) para exibir todas as propriedades e os valores de Propriedade do objeto Version.</span><span class="sxs-lookup"><span data-stu-id="e2649-124">The `Format-List` command uses the *Property* parameter with a value of all (\*) to display all of the properties and property values of the version object.</span></span>

### <span data-ttu-id="e2649-125">Exemplo 4: obter a cultura atual para o host</span><span class="sxs-lookup"><span data-stu-id="e2649-125">Example 4: Get the current culture for the host</span></span>

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

<span data-ttu-id="e2649-126">Este comando obtém informações detalhadas sobre a cultura atual definida para o Windows PowerShell em execução no host.</span><span class="sxs-lookup"><span data-stu-id="e2649-126">This command gets detailed information about the current culture set for Windows PowerShell running in the host.</span></span> <span data-ttu-id="e2649-127">Essas são as mesmas informações retornadas pelo `Get-Culture` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e2649-127">This is the same information that is returned by the `Get-Culture` cmdlet.</span></span>

<span data-ttu-id="e2649-128">Da mesma forma, a propriedade **CurrentUICulture** retorna o mesmo objeto que `Get-UICulture` retorna.</span><span class="sxs-lookup"><span data-stu-id="e2649-128">Similarly, the **CurrentUICulture** property returns the same object that `Get-UICulture` returns.</span></span>

<span data-ttu-id="e2649-129">A propriedade **CurrentCulture** do objeto de host contém um objeto **System. Globalization. CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="e2649-129">The **CurrentCulture** property of the host object contains a **System.Globalization.CultureInfo** object.</span></span> <span data-ttu-id="e2649-130">Esse comando usa um operador de pipeline (|) para enviar o objeto **CultureInfo** para o `Format-List` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e2649-130">This command uses a pipeline operator (|) to send the **CultureInfo** object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="e2649-131">O `Format-List` comando usa o parâmetro *Property* com um valor de All (\*) para exibir todas as propriedades e os valores de Propriedade do objeto **CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="e2649-131">The `Format-List` command uses the *Property* parameter with a value of all (\*) to display all of the properties and property values of the **CultureInfo** object.</span></span>

### <span data-ttu-id="e2649-132">Exemplo 5: obter o DateTimeFormat para a cultura atual</span><span class="sxs-lookup"><span data-stu-id="e2649-132">Example 5: Get the DateTimeFormat for the current culture</span></span>

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

<span data-ttu-id="e2649-133">Este comando retorna informações detalhadas sobre o DateTimeFormat da cultura atual que está sendo usada para o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2649-133">This command returns detailed information about the DateTimeFormat of the current culture that is being used for Windows PowerShell.</span></span>

<span data-ttu-id="e2649-134">A propriedade **CurrentCulture** do objeto de host contém um objeto **CultureInfo** que, por sua vez, tem muitas propriedades úteis.</span><span class="sxs-lookup"><span data-stu-id="e2649-134">The **CurrentCulture** property of the host object contains a **CultureInfo** object that, in turn, has many useful properties.</span></span> <span data-ttu-id="e2649-135">Entre elas, a propriedade **DateTimeFormat** contém um objeto **DateTimeFormatInfo** com muitas propriedades úteis.</span><span class="sxs-lookup"><span data-stu-id="e2649-135">Among them, the **DateTimeFormat** property contains a **DateTimeFormatInfo** object with many useful properties.</span></span>

<span data-ttu-id="e2649-136">Para localizar o tipo de um objeto armazenado em uma propriedade de objeto, use o `Get-Member` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e2649-136">To find the type of an object that is stored in an object property, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="e2649-137">Para exibir os valores de Propriedade do objeto, use o `Format-List` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e2649-137">To display the property values of the object, use the `Format-List` cmdlet.</span></span>

### <span data-ttu-id="e2649-138">Exemplo 6: obter a propriedade RawUI para o host</span><span class="sxs-lookup"><span data-stu-id="e2649-138">Example 6: Get the RawUI property for the host</span></span>

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

<span data-ttu-id="e2649-139">Esse comando exibe as propriedades da propriedade **rawui** do objeto de host.</span><span class="sxs-lookup"><span data-stu-id="e2649-139">This command displays the properties of the **RawUI** property of the host object.</span></span> <span data-ttu-id="e2649-140">Ao alterar esses valores, você pode alterar a aparência do programa host.</span><span class="sxs-lookup"><span data-stu-id="e2649-140">By changing these values, you can change the appearance of the host program.</span></span>

### <span data-ttu-id="e2649-141">Exemplo 7: definir a cor do plano de fundo para o console do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2649-141">Example 7: Set the background color for the PowerShell console</span></span>

```powershell
PS C:\> (Get-Host).UI.RawUI.BackgroundColor = "Black"
PS C:\> cls
```

<span data-ttu-id="e2649-142">Estes comandos alteram a cor de plano de fundo do console do Windows PowerShell para preto.</span><span class="sxs-lookup"><span data-stu-id="e2649-142">These commands change the background color of the Windows PowerShell console to black.</span></span> <span data-ttu-id="e2649-143">O comando **CLS** é um alias para a `Clear-Host` função, que limpa a tela e altera a tela inteira para a nova cor.</span><span class="sxs-lookup"><span data-stu-id="e2649-143">The **cls** command is an alias for the `Clear-Host` function, which clears the screen and changes the whole screen to the new color.</span></span>

<span data-ttu-id="e2649-144">Essa alteração entra em vigor somente na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="e2649-144">This change is effective only in the current session.</span></span> <span data-ttu-id="e2649-145">Para alterar a cor de plano de fundo do console de todas as sessões, adicione o comando ao seu perfil do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2649-145">To change the background color of the console for all sessions, add the command to your Windows PowerShell profile.</span></span>

### <span data-ttu-id="e2649-146">Exemplo 8: definir a cor do plano de fundo para mensagens de erro</span><span class="sxs-lookup"><span data-stu-id="e2649-146">Example 8: Set the background color for error messages</span></span>

```
PS C:\> $Host.PrivateData.ErrorBackgroundColor = "white"
```

<span data-ttu-id="e2649-147">Este comando altera a cor de plano de fundo das mensagens de erro para branco.</span><span class="sxs-lookup"><span data-stu-id="e2649-147">This command changes the background color of error messages to white.</span></span>

<span data-ttu-id="e2649-148">Esse comando usa a `$Host` variável automática, que contém o objeto de host para o programa de host atual.</span><span class="sxs-lookup"><span data-stu-id="e2649-148">This command uses the `$Host` automatic variable, which contains the host object for the current host program.</span></span> <span data-ttu-id="e2649-149">`Get-Host` Retorna o mesmo objeto que `$Host` contém, para que você possa usá-los de maneira intercambiável.</span><span class="sxs-lookup"><span data-stu-id="e2649-149">`Get-Host` returns the same object that `$Host` contains, so you can use them interchangeably.</span></span>

<span data-ttu-id="e2649-150">Esse comando usa a propriedade **PrivateData** de `$Host` como sua propriedade ErrorBackgroundColor.</span><span class="sxs-lookup"><span data-stu-id="e2649-150">This command uses the **PrivateData** property of `$Host` as its ErrorBackgroundColor property.</span></span> <span data-ttu-id="e2649-151">Para ver todas as propriedades do objeto no `$Host` . Propriedade PrivateData, digite `$host.privatedata | format-list *` .</span><span class="sxs-lookup"><span data-stu-id="e2649-151">To see all of the properties of the object in the `$Host`.PrivateData property, type `$host.privatedata | format-list *`.</span></span>

## <span data-ttu-id="e2649-152">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e2649-152">PARAMETERS</span></span>

### <span data-ttu-id="e2649-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e2649-153">CommonParameters</span></span>

<span data-ttu-id="e2649-154">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e2649-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e2649-155">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e2649-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e2649-156">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="e2649-156">INPUTS</span></span>

### <span data-ttu-id="e2649-157">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e2649-157">None</span></span>
<span data-ttu-id="e2649-158">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e2649-158">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="e2649-159">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="e2649-159">OUTPUTS</span></span>

### <span data-ttu-id="e2649-160">System. Management. Automation. Internal. host. InternalHost</span><span class="sxs-lookup"><span data-stu-id="e2649-160">System.Management.Automation.Internal.Host.InternalHost</span></span>

<span data-ttu-id="e2649-161">`Get-Host` Retorna um objeto **System. Management. Automation. Internal. host. InternalHost** .</span><span class="sxs-lookup"><span data-stu-id="e2649-161">`Get-Host` returns a **System.Management.Automation.Internal.Host.InternalHost** object.</span></span>

## <span data-ttu-id="e2649-162">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e2649-162">NOTES</span></span>

<span data-ttu-id="e2649-163">A `$Host` variável automática contém o mesmo objeto que `Get-Host` retorna, e você pode usá-la da mesma maneira.</span><span class="sxs-lookup"><span data-stu-id="e2649-163">The `$Host` automatic variable contains the same object that `Get-Host` returns, and you can use it in the same way.</span></span> <span data-ttu-id="e2649-164">Da mesma forma, as `$PSCulture` `$PSUICulture` variáveis e automáticas contêm os mesmos objetos que as propriedades CurrentCulture e CurrentUICulture do objeto de host contêm.</span><span class="sxs-lookup"><span data-stu-id="e2649-164">Similarly, the `$PSCulture` and `$PSUICulture` automatic variables contain the same objects that the CurrentCulture and CurrentUICulture properties of the host object contain.</span></span> <span data-ttu-id="e2649-165">Você pode usar esses recursos alternadamente.</span><span class="sxs-lookup"><span data-stu-id="e2649-165">You can use these features interchangeably.</span></span>

<span data-ttu-id="e2649-166">Para obter mais informações, consulte [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="e2649-166">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

## <span data-ttu-id="e2649-167">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e2649-167">RELATED LINKS</span></span>

[<span data-ttu-id="e2649-168">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="e2649-168">Clear-Host</span></span>](../Microsoft.PowerShell.Core/Clear-Host.md)

[<span data-ttu-id="e2649-169">Read-Host</span><span class="sxs-lookup"><span data-stu-id="e2649-169">Read-Host</span></span>](Read-Host.md)

[<span data-ttu-id="e2649-170">Write-Host</span><span class="sxs-lookup"><span data-stu-id="e2649-170">Write-Host</span></span>](Write-Host.md)

