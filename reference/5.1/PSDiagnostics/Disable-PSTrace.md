---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pstrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSTrace
ms.openlocfilehash: fc58e0bcfdd0b4ee7c7ee383b44f7d7f428c34c0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193707"
---
# <span data-ttu-id="fef14-102">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="fef14-102">Disable-PSTrace</span></span>

## <span data-ttu-id="fef14-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="fef14-103">SYNOPSIS</span></span>
<span data-ttu-id="fef14-104">Desabilita os logs do provedor de eventos Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fef14-104">Disables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="fef14-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fef14-105">SYNTAX</span></span>

```
Disable-PSTrace [-AnalyticOnly] [<CommonParameters>]
```

## <span data-ttu-id="fef14-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fef14-106">DESCRIPTION</span></span>

<span data-ttu-id="fef14-107">Esse cmdlet desabilita os logs de eventos operacionais e analíticos do provedor de eventos Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fef14-107">This cmdlet disables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="fef14-108">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="fef14-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="fef14-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="fef14-109">EXAMPLES</span></span>

### <span data-ttu-id="fef14-110">Exemplo 1: desabilitar o log de eventos analíticos para o PowerShell</span><span class="sxs-lookup"><span data-stu-id="fef14-110">Example 1: Disable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="fef14-111">O exemplo a seguir desabilita somente o log de eventos analíticos do provedor Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fef14-111">The following example disables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Disable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="fef14-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fef14-112">PARAMETERS</span></span>

### <span data-ttu-id="fef14-113">-AnalyticOnly</span><span class="sxs-lookup"><span data-stu-id="fef14-113">-AnalyticOnly</span></span>

<span data-ttu-id="fef14-114">Quando esse parâmetro é usado, o cmdlet desabilita o log de eventos analíticos do provedor Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fef14-114">When this parameter is used, the cmdlet disables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="fef14-115">O log de eventos operacional não é alterado.</span><span class="sxs-lookup"><span data-stu-id="fef14-115">The Operational event log is not changed.</span></span>

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

## <span data-ttu-id="fef14-116">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="fef14-116">INPUTS</span></span>

### <span data-ttu-id="fef14-117">Nenhum</span><span class="sxs-lookup"><span data-stu-id="fef14-117">None</span></span>

## <span data-ttu-id="fef14-118">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="fef14-118">OUTPUTS</span></span>

### <span data-ttu-id="fef14-119">System.Object</span><span class="sxs-lookup"><span data-stu-id="fef14-119">System.Object</span></span>

## <span data-ttu-id="fef14-120">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="fef14-120">NOTES</span></span>

<span data-ttu-id="fef14-121">Esse cmdlet usa os `Get-LogProperties` `Set-LogProperties` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="fef14-121">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="fef14-122">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="fef14-122">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="fef14-123">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="fef14-123">RELATED LINKS</span></span>

[<span data-ttu-id="fef14-124">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="fef14-124">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="fef14-125">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="fef14-125">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="fef14-126">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="fef14-126">Enable-PSTrace</span></span>](Enable-PSTrace.md)
