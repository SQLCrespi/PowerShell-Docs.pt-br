---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pstrace?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSTrace
ms.openlocfilehash: cc94d85e48849d47531ac0a83527f3c68c21377e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194667"
---
# <span data-ttu-id="04e59-102">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="04e59-102">Enable-PSTrace</span></span>

## <span data-ttu-id="04e59-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="04e59-103">SYNOPSIS</span></span>
<span data-ttu-id="04e59-104">Habilita os logs do provedor de eventos Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="04e59-104">Enables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="04e59-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="04e59-105">SYNTAX</span></span>

```
Enable-PSTrace [-Force] [-AnalyticOnly] [<CommonParameters>]
```

## <span data-ttu-id="04e59-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="04e59-106">DESCRIPTION</span></span>

<span data-ttu-id="04e59-107">Esse cmdlet habilita os logs de eventos operacionais e analíticos do provedor de eventos Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="04e59-107">This cmdlet enables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="04e59-108">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="04e59-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="04e59-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="04e59-109">EXAMPLES</span></span>

### <span data-ttu-id="04e59-110">Exemplo 1: habilitar o log de eventos analíticos para o PowerShell</span><span class="sxs-lookup"><span data-stu-id="04e59-110">Example 1: Enable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="04e59-111">O exemplo a seguir habilita somente o log de eventos analíticos do provedor Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="04e59-111">The following example enables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Enable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="04e59-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="04e59-112">PARAMETERS</span></span>

### <span data-ttu-id="04e59-113">-AnalyticOnly</span><span class="sxs-lookup"><span data-stu-id="04e59-113">-AnalyticOnly</span></span>

<span data-ttu-id="04e59-114">Quando esse parâmetro é usado, o cmdlet habilita o log de eventos analíticos do provedor Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="04e59-114">When this parameter is used, the cmdlet enables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="04e59-115">O log de eventos operacional não é alterado.</span><span class="sxs-lookup"><span data-stu-id="04e59-115">The Operational event log is not changed.</span></span>

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

### <span data-ttu-id="04e59-116">-Force</span><span class="sxs-lookup"><span data-stu-id="04e59-116">-Force</span></span>

<span data-ttu-id="04e59-117">Usado para forçar a alteração sem avisar.</span><span class="sxs-lookup"><span data-stu-id="04e59-117">Used to force the change without prompting.</span></span>

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

### <span data-ttu-id="04e59-118">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="04e59-118">CommonParameters</span></span>
<span data-ttu-id="04e59-119">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="04e59-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="04e59-120">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="04e59-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="04e59-121">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="04e59-121">INPUTS</span></span>

### <span data-ttu-id="04e59-122">Nenhum</span><span class="sxs-lookup"><span data-stu-id="04e59-122">None</span></span>

## <span data-ttu-id="04e59-123">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="04e59-123">OUTPUTS</span></span>

### <span data-ttu-id="04e59-124">Nenhum</span><span class="sxs-lookup"><span data-stu-id="04e59-124">None</span></span>

## <span data-ttu-id="04e59-125">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="04e59-125">NOTES</span></span>

<span data-ttu-id="04e59-126">Esse cmdlet usa os `Get-LogProperties` `Set-LogProperties` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="04e59-126">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="04e59-127">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="04e59-127">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="04e59-128">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="04e59-128">RELATED LINKS</span></span>

[<span data-ttu-id="04e59-129">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="04e59-129">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="04e59-130">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="04e59-130">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="04e59-131">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="04e59-131">Disable-PSTrace</span></span>](Disable-PSTrace.md)

