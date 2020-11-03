---
external help file: PSDiagnostics-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/stop-trace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Trace
ms.openlocfilehash: 2629ae1beb722282065e76600174b511bfe5fbc9
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193095"
---
# <span data-ttu-id="5762a-103">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="5762a-103">Stop-Trace</span></span>

## <span data-ttu-id="5762a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="5762a-104">SYNOPSIS</span></span>
<span data-ttu-id="5762a-105">Interromper uma sessão de log de rastreamento de eventos.</span><span class="sxs-lookup"><span data-stu-id="5762a-105">Stop an Event Trace logging session.</span></span>

## <span data-ttu-id="5762a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5762a-106">SYNTAX</span></span>

```
Stop-Trace [-SessionName] <Object> [-ETS] [<CommonParameters>]
```

## <span data-ttu-id="5762a-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5762a-107">DESCRIPTION</span></span>

<span data-ttu-id="5762a-108">Esse cmdlet interrompe uma sessão de log de rastreamento de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="5762a-108">This cmdlet stops a Windows Event Trace logging session.</span></span>

<span data-ttu-id="5762a-109">Esse cmdlet é usado pelos seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="5762a-109">This cmdlet is used by the following cmdlets:</span></span>

- `Disable-PSWSManCombinedTrace`
- `Disable-WSManTrace`

<span data-ttu-id="5762a-110">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="5762a-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="5762a-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="5762a-111">EXAMPLES</span></span>

### <span data-ttu-id="5762a-112">Exemplo 1: parar uma sessão de log de rastreamento do WSMan</span><span class="sxs-lookup"><span data-stu-id="5762a-112">Example 1: Stop a WSMan Trace logging session</span></span>

```powershell
Stop-Trace -SessionName 'wsmlog'
```

## <span data-ttu-id="5762a-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5762a-113">PARAMETERS</span></span>

### <span data-ttu-id="5762a-114">-ETS</span><span class="sxs-lookup"><span data-stu-id="5762a-114">-ETS</span></span>
<span data-ttu-id="5762a-115">Envie comandos para sessões de rastreamento de eventos diretamente sem salvar ou agendar.</span><span class="sxs-lookup"><span data-stu-id="5762a-115">Send commands to Event Trace Sessions directly without saving or scheduling.</span></span>

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

### <span data-ttu-id="5762a-116">-SESSIONNAME</span><span class="sxs-lookup"><span data-stu-id="5762a-116">-SessionName</span></span>
<span data-ttu-id="5762a-117">O nome da sessão de rastreamento de eventos a ser interrompida.</span><span class="sxs-lookup"><span data-stu-id="5762a-117">The name of the Event Trace session to be stopped.</span></span>

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

### <span data-ttu-id="5762a-118">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5762a-118">CommonParameters</span></span>
<span data-ttu-id="5762a-119">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5762a-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5762a-120">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5762a-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5762a-121">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="5762a-121">INPUTS</span></span>

### <span data-ttu-id="5762a-122">Nenhum</span><span class="sxs-lookup"><span data-stu-id="5762a-122">None</span></span>

## <span data-ttu-id="5762a-123">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="5762a-123">OUTPUTS</span></span>

### <span data-ttu-id="5762a-124">Nenhum</span><span class="sxs-lookup"><span data-stu-id="5762a-124">None</span></span>

## <span data-ttu-id="5762a-125">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="5762a-125">NOTES</span></span>

## <span data-ttu-id="5762a-126">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="5762a-126">RELATED LINKS</span></span>

[<span data-ttu-id="5762a-127">Rastreamento de eventos</span><span class="sxs-lookup"><span data-stu-id="5762a-127">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="5762a-128">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="5762a-128">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="5762a-129">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="5762a-129">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

[<span data-ttu-id="5762a-130">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="5762a-130">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)

[<span data-ttu-id="5762a-131">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="5762a-131">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)

[<span data-ttu-id="5762a-132">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="5762a-132">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)
