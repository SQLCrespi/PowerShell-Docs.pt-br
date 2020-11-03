---
external help file: PSDiagnostics-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pswsmancombinedtrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSWSManCombinedTrace
ms.openlocfilehash: 4a98941de072b9b57b89a25bc180c0ee391d8b63
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193706"
---
# <span data-ttu-id="4160a-103">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="4160a-103">Disable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="4160a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="4160a-104">SYNOPSIS</span></span>
<span data-ttu-id="4160a-105">Pare a sessão de log iniciada por Enable-PSWSManCombinedTrace.</span><span class="sxs-lookup"><span data-stu-id="4160a-105">Stop the logging session started by Enable-PSWSManCombinedTrace.</span></span>

## <span data-ttu-id="4160a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4160a-106">SYNTAX</span></span>

```
Disable-PSWSManCombinedTrace [<CommonParameters>]
```

## <span data-ttu-id="4160a-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4160a-107">DESCRIPTION</span></span>

<span data-ttu-id="4160a-108">Esse cmdlet interrompe a sessão de log iniciada pelo `Enable-PSWSManCombinedTrace` .</span><span class="sxs-lookup"><span data-stu-id="4160a-108">This cmdlet stops the logging session started by `Enable-PSWSManCombinedTrace`.</span></span>

<span data-ttu-id="4160a-109">Esse cmdlet usa o `Stop-Trace` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4160a-109">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="4160a-110">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="4160a-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="4160a-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="4160a-111">EXAMPLES</span></span>

### <span data-ttu-id="4160a-112">Exemplo 1: desabilitar a sessão de log combinada</span><span class="sxs-lookup"><span data-stu-id="4160a-112">Example 1: Disable the combined logging session</span></span>

```powershell
Disable-PSWSManCombinedTrace
```

## <span data-ttu-id="4160a-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4160a-113">PARAMETERS</span></span>

### <span data-ttu-id="4160a-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4160a-114">CommonParameters</span></span>

<span data-ttu-id="4160a-115">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4160a-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4160a-116">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4160a-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4160a-117">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="4160a-117">INPUTS</span></span>

### <span data-ttu-id="4160a-118">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4160a-118">None</span></span>

## <span data-ttu-id="4160a-119">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="4160a-119">OUTPUTS</span></span>

### <span data-ttu-id="4160a-120">System.Object</span><span class="sxs-lookup"><span data-stu-id="4160a-120">System.Object</span></span>

## <span data-ttu-id="4160a-121">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="4160a-121">NOTES</span></span>

## <span data-ttu-id="4160a-122">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="4160a-122">RELATED LINKS</span></span>

[<span data-ttu-id="4160a-123">Rastreamento de eventos</span><span class="sxs-lookup"><span data-stu-id="4160a-123">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="4160a-124">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="4160a-124">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="4160a-125">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="4160a-125">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)
