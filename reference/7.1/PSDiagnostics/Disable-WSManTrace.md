---
external help file: PSDiagnostics-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-wsmantrace?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManTrace
ms.openlocfilehash: 5566fb2e11311990cea76e6802c84985795c3553
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "93192629"
---
# <span data-ttu-id="c4372-103">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="c4372-103">Disable-WSManTrace</span></span>

## <span data-ttu-id="c4372-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="c4372-104">SYNOPSIS</span></span>
<span data-ttu-id="c4372-105">Pare a sessão de registro em log do WSMan iniciada por Enable-WSManTrace.</span><span class="sxs-lookup"><span data-stu-id="c4372-105">Stop the WSMan logging session started by Enable-WSManTrace.</span></span>

## <span data-ttu-id="c4372-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c4372-106">SYNTAX</span></span>

```
Disable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="c4372-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c4372-107">DESCRIPTION</span></span>
<span data-ttu-id="c4372-108">Esse cmdlet interrompe a sessão de registro em log do WSMan iniciada por Enable-WSManTrace.</span><span class="sxs-lookup"><span data-stu-id="c4372-108">This cmdlet stops the WSMan logging session started by Enable-WSManTrace.</span></span>

<span data-ttu-id="c4372-109">Esse cmdlet usa o `Stop-Trace` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c4372-109">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="c4372-110">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="c4372-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="c4372-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="c4372-111">EXAMPLES</span></span>

### <span data-ttu-id="c4372-112">Exemplo 1: parar um rastreamento WSMan</span><span class="sxs-lookup"><span data-stu-id="c4372-112">Example 1: Stop a WSMan trace</span></span>

```powershell
Disable-WSManTrace
```

## <span data-ttu-id="c4372-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c4372-113">PARAMETERS</span></span>

### <span data-ttu-id="c4372-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c4372-114">CommonParameters</span></span>

<span data-ttu-id="c4372-115">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c4372-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c4372-116">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c4372-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c4372-117">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="c4372-117">INPUTS</span></span>

### <span data-ttu-id="c4372-118">Nenhum</span><span class="sxs-lookup"><span data-stu-id="c4372-118">None</span></span>

## <span data-ttu-id="c4372-119">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="c4372-119">OUTPUTS</span></span>

### <span data-ttu-id="c4372-120">Nenhum</span><span class="sxs-lookup"><span data-stu-id="c4372-120">None</span></span>

## <span data-ttu-id="c4372-121">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="c4372-121">NOTES</span></span>

## <span data-ttu-id="c4372-122">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="c4372-122">RELATED LINKS</span></span>

[<span data-ttu-id="c4372-123">Rastreamento de eventos</span><span class="sxs-lookup"><span data-stu-id="c4372-123">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="c4372-124">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="c4372-124">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="c4372-125">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="c4372-125">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)

