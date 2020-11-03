---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pstrace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSTrace
ms.openlocfilehash: fea84d9ae83eae88f9a665e8a49aaf2e6743127d
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193156"
---
# <span data-ttu-id="348d8-102">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="348d8-102">Enable-PSTrace</span></span>

## <span data-ttu-id="348d8-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="348d8-103">SYNOPSIS</span></span>
<span data-ttu-id="348d8-104">Habilita os logs do provedor de eventos Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="348d8-104">Enables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="348d8-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="348d8-105">SYNTAX</span></span>

```
Enable-PSTrace [-Force] [-AnalyticOnly] [<CommonParameters>]
```

## <span data-ttu-id="348d8-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="348d8-106">DESCRIPTION</span></span>

<span data-ttu-id="348d8-107">Esse cmdlet habilita os logs de eventos operacionais e analíticos do provedor de eventos Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="348d8-107">This cmdlet enables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="348d8-108">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="348d8-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="348d8-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="348d8-109">EXAMPLES</span></span>

### <span data-ttu-id="348d8-110">Exemplo 1: habilitar o log de eventos analíticos para o PowerShell</span><span class="sxs-lookup"><span data-stu-id="348d8-110">Example 1: Enable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="348d8-111">O exemplo a seguir habilita somente o log de eventos analíticos do provedor Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="348d8-111">The following example enables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Enable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="348d8-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="348d8-112">PARAMETERS</span></span>

### <span data-ttu-id="348d8-113">-AnalyticOnly</span><span class="sxs-lookup"><span data-stu-id="348d8-113">-AnalyticOnly</span></span>

<span data-ttu-id="348d8-114">Quando esse parâmetro é usado, o cmdlet habilita o log de eventos analíticos do provedor Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="348d8-114">When this parameter is used, the cmdlet enables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="348d8-115">O log de eventos operacional não é alterado.</span><span class="sxs-lookup"><span data-stu-id="348d8-115">The Operational event log is not changed.</span></span>

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

### <span data-ttu-id="348d8-116">-Force</span><span class="sxs-lookup"><span data-stu-id="348d8-116">-Force</span></span>

<span data-ttu-id="348d8-117">Usado para forçar a alteração sem avisar.</span><span class="sxs-lookup"><span data-stu-id="348d8-117">Used to force the change without prompting.</span></span>

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

### <span data-ttu-id="348d8-118">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="348d8-118">CommonParameters</span></span>
<span data-ttu-id="348d8-119">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="348d8-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="348d8-120">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="348d8-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="348d8-121">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="348d8-121">INPUTS</span></span>

### <span data-ttu-id="348d8-122">Nenhum</span><span class="sxs-lookup"><span data-stu-id="348d8-122">None</span></span>

## <span data-ttu-id="348d8-123">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="348d8-123">OUTPUTS</span></span>

### <span data-ttu-id="348d8-124">Nenhum</span><span class="sxs-lookup"><span data-stu-id="348d8-124">None</span></span>

## <span data-ttu-id="348d8-125">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="348d8-125">NOTES</span></span>

<span data-ttu-id="348d8-126">Esse cmdlet usa os `Get-LogProperties` `Set-LogProperties` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="348d8-126">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="348d8-127">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="348d8-127">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="348d8-128">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="348d8-128">RELATED LINKS</span></span>

[<span data-ttu-id="348d8-129">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="348d8-129">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="348d8-130">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="348d8-130">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="348d8-131">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="348d8-131">Disable-PSTrace</span></span>](Disable-PSTrace.md)
