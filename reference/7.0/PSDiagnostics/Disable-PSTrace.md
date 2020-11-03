---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pstrace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSTrace
ms.openlocfilehash: 50ad2d48faee88c196942b13141d3ad57c51fdeb
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192834"
---
# <span data-ttu-id="efaa4-102">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="efaa4-102">Disable-PSTrace</span></span>

## <span data-ttu-id="efaa4-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="efaa4-103">SYNOPSIS</span></span>
<span data-ttu-id="efaa4-104">Desabilita os logs do provedor de eventos Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="efaa4-104">Disables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="efaa4-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="efaa4-105">SYNTAX</span></span>

```
Disable-PSTrace [-AnalyticOnly] [<CommonParameters>]
```

## <span data-ttu-id="efaa4-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="efaa4-106">DESCRIPTION</span></span>

<span data-ttu-id="efaa4-107">Esse cmdlet desabilita os logs de eventos operacionais e analíticos do provedor de eventos Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="efaa4-107">This cmdlet disables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="efaa4-108">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="efaa4-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="efaa4-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="efaa4-109">EXAMPLES</span></span>

### <span data-ttu-id="efaa4-110">Exemplo 1: desabilitar o log de eventos analíticos para o PowerShell</span><span class="sxs-lookup"><span data-stu-id="efaa4-110">Example 1: Disable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="efaa4-111">O exemplo a seguir desabilita somente o log de eventos analíticos do provedor Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="efaa4-111">The following example disables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Disable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="efaa4-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="efaa4-112">PARAMETERS</span></span>

### <span data-ttu-id="efaa4-113">-AnalyticOnly</span><span class="sxs-lookup"><span data-stu-id="efaa4-113">-AnalyticOnly</span></span>

<span data-ttu-id="efaa4-114">Quando esse parâmetro é usado, o cmdlet desabilita o log de eventos analíticos do provedor Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="efaa4-114">When this parameter is used, the cmdlet disables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="efaa4-115">O log de eventos operacional não é alterado.</span><span class="sxs-lookup"><span data-stu-id="efaa4-115">The Operational event log is not changed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="efaa4-116">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="efaa4-116">CommonParameters</span></span>
<span data-ttu-id="efaa4-117">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="efaa4-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="efaa4-118">Para obter mais informações, confira [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="efaa4-118">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="efaa4-119">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="efaa4-119">INPUTS</span></span>

### <span data-ttu-id="efaa4-120">Nenhum</span><span class="sxs-lookup"><span data-stu-id="efaa4-120">None</span></span>

## <span data-ttu-id="efaa4-121">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="efaa4-121">OUTPUTS</span></span>

### <span data-ttu-id="efaa4-122">Nenhum</span><span class="sxs-lookup"><span data-stu-id="efaa4-122">None</span></span>

## <span data-ttu-id="efaa4-123">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="efaa4-123">NOTES</span></span>

<span data-ttu-id="efaa4-124">Esse cmdlet usa os `Get-LogProperties` `Set-LogProperties` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="efaa4-124">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="efaa4-125">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="efaa4-125">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="efaa4-126">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="efaa4-126">RELATED LINKS</span></span>

[<span data-ttu-id="efaa4-127">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="efaa4-127">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="efaa4-128">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="efaa4-128">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="efaa4-129">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="efaa4-129">Enable-PSTrace</span></span>](Enable-PSTrace.md)
