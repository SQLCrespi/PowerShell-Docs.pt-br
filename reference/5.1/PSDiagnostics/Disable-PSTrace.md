---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pstrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSTrace
ms.openlocfilehash: 50d4118c5805a59d291d8dd17f467e7b47d34b46
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103194515"
---
# <span data-ttu-id="b98b5-102">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="b98b5-102">Disable-PSTrace</span></span>

## <span data-ttu-id="b98b5-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b98b5-103">SYNOPSIS</span></span>
<span data-ttu-id="b98b5-104">Desabilita os logs do provedor de eventos Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b98b5-104">Disables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="b98b5-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b98b5-105">SYNTAX</span></span>

```
Disable-PSTrace [-AnalyticOnly] [<CommonParameters>]
```

## <span data-ttu-id="b98b5-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b98b5-106">DESCRIPTION</span></span>

<span data-ttu-id="b98b5-107">Esse cmdlet desabilita os logs de eventos operacionais e analíticos do provedor de eventos Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b98b5-107">This cmdlet disables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="b98b5-108">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="b98b5-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="b98b5-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b98b5-109">EXAMPLES</span></span>

### <span data-ttu-id="b98b5-110">Exemplo 1: desabilitar o log de eventos analíticos para o PowerShell</span><span class="sxs-lookup"><span data-stu-id="b98b5-110">Example 1: Disable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="b98b5-111">O exemplo a seguir desabilita somente o log de eventos analíticos do provedor Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b98b5-111">The following example disables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Disable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="b98b5-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b98b5-112">PARAMETERS</span></span>

### <span data-ttu-id="b98b5-113">-AnalyticOnly</span><span class="sxs-lookup"><span data-stu-id="b98b5-113">-AnalyticOnly</span></span>

<span data-ttu-id="b98b5-114">Quando esse parâmetro é usado, o cmdlet desabilita o log de eventos analíticos do provedor Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b98b5-114">When this parameter is used, the cmdlet disables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="b98b5-115">O log de eventos operacional não é alterado.</span><span class="sxs-lookup"><span data-stu-id="b98b5-115">The Operational event log is not changed.</span></span>

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

## <span data-ttu-id="b98b5-116">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b98b5-116">INPUTS</span></span>

### <span data-ttu-id="b98b5-117">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b98b5-117">None</span></span>

## <span data-ttu-id="b98b5-118">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b98b5-118">OUTPUTS</span></span>

### <span data-ttu-id="b98b5-119">System.Object</span><span class="sxs-lookup"><span data-stu-id="b98b5-119">System.Object</span></span>

## <span data-ttu-id="b98b5-120">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b98b5-120">NOTES</span></span>

<span data-ttu-id="b98b5-121">Esse cmdlet usa os `Get-LogProperties` `Set-LogProperties` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="b98b5-121">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="b98b5-122">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="b98b5-122">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="b98b5-123">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b98b5-123">RELATED LINKS</span></span>

[<span data-ttu-id="b98b5-124">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="b98b5-124">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="b98b5-125">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="b98b5-125">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="b98b5-126">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="b98b5-126">Enable-PSTrace</span></span>](Enable-PSTrace.md)
