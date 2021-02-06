---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/stop-trace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Trace
ms.openlocfilehash: 5727ae52326830fa16012722d0b801b7d43e50dd
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595757"
---
# <span data-ttu-id="499de-102">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="499de-102">Stop-Trace</span></span>

## <span data-ttu-id="499de-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="499de-103">SYNOPSIS</span></span>
<span data-ttu-id="499de-104">Interromper uma sessão de log de rastreamento de eventos.</span><span class="sxs-lookup"><span data-stu-id="499de-104">Stop an Event Trace logging session.</span></span>

## <span data-ttu-id="499de-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="499de-105">SYNTAX</span></span>

```
Stop-Trace [-SessionName] <Object> [-ETS] [<CommonParameters>]
```

## <span data-ttu-id="499de-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="499de-106">DESCRIPTION</span></span>

<span data-ttu-id="499de-107">Esse cmdlet interrompe uma sessão de log de rastreamento de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="499de-107">This cmdlet stops a Windows Event Trace logging session.</span></span>

<span data-ttu-id="499de-108">Esse cmdlet é usado pelos seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="499de-108">This cmdlet is used by the following cmdlets:</span></span>

- `Disable-PSWSManCombinedTrace`
- `Disable-WSManTrace`

<span data-ttu-id="499de-109">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="499de-109">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="499de-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="499de-110">EXAMPLES</span></span>

### <span data-ttu-id="499de-111">Exemplo 1: parar uma sessão de log de rastreamento do WSMan</span><span class="sxs-lookup"><span data-stu-id="499de-111">Example 1: Stop a WSMan Trace logging session</span></span>

```powershell
Stop-Trace -SessionName 'wsmlog'
```

## <span data-ttu-id="499de-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="499de-112">PARAMETERS</span></span>

### <span data-ttu-id="499de-113">-ETS</span><span class="sxs-lookup"><span data-stu-id="499de-113">-ETS</span></span>
<span data-ttu-id="499de-114">Envie comandos para sessões de rastreamento de eventos diretamente sem salvar ou agendar.</span><span class="sxs-lookup"><span data-stu-id="499de-114">Send commands to Event Trace Sessions directly without saving or scheduling.</span></span>

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

### <span data-ttu-id="499de-115">-SESSIONNAME</span><span class="sxs-lookup"><span data-stu-id="499de-115">-SessionName</span></span>
<span data-ttu-id="499de-116">O nome da sessão de rastreamento de eventos a ser interrompida.</span><span class="sxs-lookup"><span data-stu-id="499de-116">The name of the Event Trace session to be stopped.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="499de-117">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="499de-117">CommonParameters</span></span>
<span data-ttu-id="499de-118">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="499de-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="499de-119">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="499de-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="499de-120">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="499de-120">INPUTS</span></span>

### <span data-ttu-id="499de-121">Nenhum</span><span class="sxs-lookup"><span data-stu-id="499de-121">None</span></span>

## <span data-ttu-id="499de-122">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="499de-122">OUTPUTS</span></span>

### <span data-ttu-id="499de-123">Nenhum</span><span class="sxs-lookup"><span data-stu-id="499de-123">None</span></span>

## <span data-ttu-id="499de-124">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="499de-124">NOTES</span></span>

## <span data-ttu-id="499de-125">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="499de-125">RELATED LINKS</span></span>

[<span data-ttu-id="499de-126">Rastreamento de eventos</span><span class="sxs-lookup"><span data-stu-id="499de-126">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="499de-127">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="499de-127">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="499de-128">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="499de-128">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

[<span data-ttu-id="499de-129">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="499de-129">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)

[<span data-ttu-id="499de-130">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="499de-130">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)

[<span data-ttu-id="499de-131">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="499de-131">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)

