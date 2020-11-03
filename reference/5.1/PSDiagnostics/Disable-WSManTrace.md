---
external help file: PSDiagnostics-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-wsmantrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManTrace
ms.openlocfilehash: 90cb571f93243e6fbc59970e5602911e17e25ec7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193703"
---
# <span data-ttu-id="1fee9-103">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="1fee9-103">Disable-WSManTrace</span></span>

## <span data-ttu-id="1fee9-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="1fee9-104">SYNOPSIS</span></span>
<span data-ttu-id="1fee9-105">Pare a sessão de registro em log do WSMan iniciada por Enable-WSManTrace.</span><span class="sxs-lookup"><span data-stu-id="1fee9-105">Stop the WSMan logging session started by Enable-WSManTrace.</span></span>

## <span data-ttu-id="1fee9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1fee9-106">SYNTAX</span></span>

```
Disable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="1fee9-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1fee9-107">DESCRIPTION</span></span>
<span data-ttu-id="1fee9-108">Esse cmdlet interrompe a sessão de registro em log do WSMan iniciada por Enable-WSManTrace.</span><span class="sxs-lookup"><span data-stu-id="1fee9-108">This cmdlet stops the WSMan logging session started by Enable-WSManTrace.</span></span>

<span data-ttu-id="1fee9-109">Esse cmdlet usa o `Stop-Trace` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1fee9-109">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="1fee9-110">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="1fee9-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="1fee9-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="1fee9-111">EXAMPLES</span></span>

### <span data-ttu-id="1fee9-112">Exemplo 1: parar um rastreamento WSMan</span><span class="sxs-lookup"><span data-stu-id="1fee9-112">Example 1: Stop a WSMan trace</span></span>

```powershell
Disable-WSManTrace
```

## <span data-ttu-id="1fee9-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1fee9-113">PARAMETERS</span></span>

### <span data-ttu-id="1fee9-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1fee9-114">CommonParameters</span></span>

<span data-ttu-id="1fee9-115">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1fee9-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1fee9-116">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1fee9-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1fee9-117">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="1fee9-117">INPUTS</span></span>

### <span data-ttu-id="1fee9-118">Nenhum</span><span class="sxs-lookup"><span data-stu-id="1fee9-118">None</span></span>

## <span data-ttu-id="1fee9-119">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="1fee9-119">OUTPUTS</span></span>

### <span data-ttu-id="1fee9-120">System.Object</span><span class="sxs-lookup"><span data-stu-id="1fee9-120">System.Object</span></span>

## <span data-ttu-id="1fee9-121">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="1fee9-121">NOTES</span></span>

## <span data-ttu-id="1fee9-122">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="1fee9-122">RELATED LINKS</span></span>

[<span data-ttu-id="1fee9-123">Rastreamento de eventos</span><span class="sxs-lookup"><span data-stu-id="1fee9-123">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="1fee9-124">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="1fee9-124">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="1fee9-125">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="1fee9-125">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)
