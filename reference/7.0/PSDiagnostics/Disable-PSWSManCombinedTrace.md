---
external help file: PSDiagnostics-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pswsmancombinedtrace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSWSManCombinedTrace
ms.openlocfilehash: 4a00b843e5e4ec73cf98f4c924ca24a3e1ee0700
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "93192673"
---
# <span data-ttu-id="e628d-103">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="e628d-103">Disable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="e628d-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="e628d-104">SYNOPSIS</span></span>
<span data-ttu-id="e628d-105">Pare a sessão de log iniciada por Enable-PSWSManCombinedTrace.</span><span class="sxs-lookup"><span data-stu-id="e628d-105">Stop the logging session started by Enable-PSWSManCombinedTrace.</span></span>

## <span data-ttu-id="e628d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e628d-106">SYNTAX</span></span>

```
Disable-PSWSManCombinedTrace [<CommonParameters>]
```

## <span data-ttu-id="e628d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e628d-107">DESCRIPTION</span></span>

<span data-ttu-id="e628d-108">Esse cmdlet interrompe a sessão de log iniciada pelo `Enable-PSWSManCombinedTrace` .</span><span class="sxs-lookup"><span data-stu-id="e628d-108">This cmdlet stops the logging session started by `Enable-PSWSManCombinedTrace`.</span></span>

<span data-ttu-id="e628d-109">Esse cmdlet usa o `Stop-Trace` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e628d-109">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="e628d-110">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="e628d-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="e628d-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e628d-111">EXAMPLES</span></span>

### <span data-ttu-id="e628d-112">Exemplo 1: desabilitar a sessão de log combinada</span><span class="sxs-lookup"><span data-stu-id="e628d-112">Example 1: Disable the combined logging session</span></span>

```powershell
Disable-PSWSManCombinedTrace
```

## <span data-ttu-id="e628d-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e628d-113">PARAMETERS</span></span>

### <span data-ttu-id="e628d-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e628d-114">CommonParameters</span></span>

<span data-ttu-id="e628d-115">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e628d-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e628d-116">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e628d-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e628d-117">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="e628d-117">INPUTS</span></span>

### <span data-ttu-id="e628d-118">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e628d-118">None</span></span>

## <span data-ttu-id="e628d-119">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="e628d-119">OUTPUTS</span></span>

### <span data-ttu-id="e628d-120">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e628d-120">None</span></span>

## <span data-ttu-id="e628d-121">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e628d-121">NOTES</span></span>

## <span data-ttu-id="e628d-122">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e628d-122">RELATED LINKS</span></span>

[<span data-ttu-id="e628d-123">Rastreamento de eventos</span><span class="sxs-lookup"><span data-stu-id="e628d-123">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="e628d-124">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="e628d-124">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="e628d-125">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="e628d-125">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)
