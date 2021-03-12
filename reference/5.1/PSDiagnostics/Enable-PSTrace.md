---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pstrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSTrace
ms.openlocfilehash: 2ec01393a46de84b59f06995473bdff6bd5b2b4f
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103195020"
---
# <span data-ttu-id="438fe-102">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="438fe-102">Enable-PSTrace</span></span>

## <span data-ttu-id="438fe-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="438fe-103">SYNOPSIS</span></span>
<span data-ttu-id="438fe-104">Habilita os logs do provedor de eventos Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="438fe-104">Enables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="438fe-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="438fe-105">SYNTAX</span></span>

```
Enable-PSTrace [-Force] [-AnalyticOnly]
```

## <span data-ttu-id="438fe-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="438fe-106">DESCRIPTION</span></span>

<span data-ttu-id="438fe-107">Esse cmdlet habilita os logs de eventos operacionais e analíticos do provedor de eventos Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="438fe-107">This cmdlet enables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="438fe-108">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="438fe-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="438fe-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="438fe-109">EXAMPLES</span></span>

### <span data-ttu-id="438fe-110">Exemplo 1: habilitar o log de eventos analíticos para o PowerShell</span><span class="sxs-lookup"><span data-stu-id="438fe-110">Example 1: Enable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="438fe-111">O exemplo a seguir habilita somente o log de eventos analíticos do provedor Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="438fe-111">The following example enables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Enable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="438fe-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="438fe-112">PARAMETERS</span></span>

### <span data-ttu-id="438fe-113">-AnalyticOnly</span><span class="sxs-lookup"><span data-stu-id="438fe-113">-AnalyticOnly</span></span>

<span data-ttu-id="438fe-114">Quando esse parâmetro é usado, o cmdlet habilita o log de eventos analíticos do provedor Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="438fe-114">When this parameter is used, the cmdlet enables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="438fe-115">O log de eventos operacional não é alterado.</span><span class="sxs-lookup"><span data-stu-id="438fe-115">The Operational event log is not changed.</span></span>

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

### <span data-ttu-id="438fe-116">-Force</span><span class="sxs-lookup"><span data-stu-id="438fe-116">-Force</span></span>

<span data-ttu-id="438fe-117">Usado para forçar a alteração sem avisar.</span><span class="sxs-lookup"><span data-stu-id="438fe-117">Used to force the change without prompting.</span></span>

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

## <span data-ttu-id="438fe-118">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="438fe-118">INPUTS</span></span>

### <span data-ttu-id="438fe-119">Nenhum</span><span class="sxs-lookup"><span data-stu-id="438fe-119">None</span></span>

## <span data-ttu-id="438fe-120">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="438fe-120">OUTPUTS</span></span>

### <span data-ttu-id="438fe-121">System.Object</span><span class="sxs-lookup"><span data-stu-id="438fe-121">System.Object</span></span>

## <span data-ttu-id="438fe-122">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="438fe-122">NOTES</span></span>

<span data-ttu-id="438fe-123">Esse cmdlet usa os `Get-LogProperties` `Set-LogProperties` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="438fe-123">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="438fe-124">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="438fe-124">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="438fe-125">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="438fe-125">RELATED LINKS</span></span>

[<span data-ttu-id="438fe-126">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="438fe-126">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="438fe-127">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="438fe-127">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="438fe-128">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="438fe-128">Disable-PSTrace</span></span>](Disable-PSTrace.md)
