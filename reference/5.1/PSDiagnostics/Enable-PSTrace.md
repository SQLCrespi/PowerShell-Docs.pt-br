---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pstrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSTrace
ms.openlocfilehash: 9abc91086d42ec7b813695e241820947f7fb0acc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193702"
---
# <span data-ttu-id="5b4b2-102">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="5b4b2-102">Enable-PSTrace</span></span>

## <span data-ttu-id="5b4b2-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="5b4b2-103">SYNOPSIS</span></span>
<span data-ttu-id="5b4b2-104">Habilita os logs do provedor de eventos Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b4b2-104">Enables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="5b4b2-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5b4b2-105">SYNTAX</span></span>

```
Enable-PSTrace [-Force] [-AnalyticOnly]
```

## <span data-ttu-id="5b4b2-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5b4b2-106">DESCRIPTION</span></span>

<span data-ttu-id="5b4b2-107">Esse cmdlet habilita os logs de eventos operacionais e analíticos do provedor de eventos Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b4b2-107">This cmdlet enables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="5b4b2-108">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="5b4b2-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="5b4b2-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="5b4b2-109">EXAMPLES</span></span>

### <span data-ttu-id="5b4b2-110">Exemplo 1: habilitar o log de eventos analíticos para o PowerShell</span><span class="sxs-lookup"><span data-stu-id="5b4b2-110">Example 1: Enable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="5b4b2-111">O exemplo a seguir habilita somente o log de eventos analíticos do provedor Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b4b2-111">The following example enables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Enable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="5b4b2-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5b4b2-112">PARAMETERS</span></span>

### <span data-ttu-id="5b4b2-113">-AnalyticOnly</span><span class="sxs-lookup"><span data-stu-id="5b4b2-113">-AnalyticOnly</span></span>

<span data-ttu-id="5b4b2-114">Quando esse parâmetro é usado, o cmdlet habilita o log de eventos analíticos do provedor Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b4b2-114">When this parameter is used, the cmdlet enables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="5b4b2-115">O log de eventos operacional não é alterado.</span><span class="sxs-lookup"><span data-stu-id="5b4b2-115">The Operational event log is not changed.</span></span>

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

### <span data-ttu-id="5b4b2-116">-Force</span><span class="sxs-lookup"><span data-stu-id="5b4b2-116">-Force</span></span>

<span data-ttu-id="5b4b2-117">Usado para forçar a alteração sem avisar.</span><span class="sxs-lookup"><span data-stu-id="5b4b2-117">Used to force the change without prompting.</span></span>

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

## <span data-ttu-id="5b4b2-118">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="5b4b2-118">INPUTS</span></span>

### <span data-ttu-id="5b4b2-119">Nenhum</span><span class="sxs-lookup"><span data-stu-id="5b4b2-119">None</span></span>

## <span data-ttu-id="5b4b2-120">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="5b4b2-120">OUTPUTS</span></span>

### <span data-ttu-id="5b4b2-121">System.Object</span><span class="sxs-lookup"><span data-stu-id="5b4b2-121">System.Object</span></span>

## <span data-ttu-id="5b4b2-122">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="5b4b2-122">NOTES</span></span>

<span data-ttu-id="5b4b2-123">Esse cmdlet usa os `Get-LogProperties` `Set-LogProperties` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="5b4b2-123">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="5b4b2-124">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="5b4b2-124">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="5b4b2-125">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="5b4b2-125">RELATED LINKS</span></span>

[<span data-ttu-id="5b4b2-126">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="5b4b2-126">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="5b4b2-127">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="5b4b2-127">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="5b4b2-128">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="5b4b2-128">Disable-PSTrace</span></span>](Disable-PSTrace.md)
