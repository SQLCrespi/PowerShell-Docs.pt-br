---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pswsmancombinedtrace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSWSManCombinedTrace
ms.openlocfilehash: 690a8b050fd0e16033a585df210db340f41a83a3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597384"
---
# <span data-ttu-id="d7ef7-102">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="d7ef7-102">Disable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="d7ef7-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d7ef7-103">SYNOPSIS</span></span>
<span data-ttu-id="d7ef7-104">Pare a sessão de log iniciada por Enable-PSWSManCombinedTrace.</span><span class="sxs-lookup"><span data-stu-id="d7ef7-104">Stop the logging session started by Enable-PSWSManCombinedTrace.</span></span>

## <span data-ttu-id="d7ef7-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d7ef7-105">SYNTAX</span></span>

```
Disable-PSWSManCombinedTrace [<CommonParameters>]
```

## <span data-ttu-id="d7ef7-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d7ef7-106">DESCRIPTION</span></span>

<span data-ttu-id="d7ef7-107">Esse cmdlet interrompe a sessão de log iniciada pelo `Enable-PSWSManCombinedTrace` .</span><span class="sxs-lookup"><span data-stu-id="d7ef7-107">This cmdlet stops the logging session started by `Enable-PSWSManCombinedTrace`.</span></span>

<span data-ttu-id="d7ef7-108">Esse cmdlet usa o `Stop-Trace` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d7ef7-108">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="d7ef7-109">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="d7ef7-109">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="d7ef7-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d7ef7-110">EXAMPLES</span></span>

### <span data-ttu-id="d7ef7-111">Exemplo 1: desabilitar a sessão de log combinada</span><span class="sxs-lookup"><span data-stu-id="d7ef7-111">Example 1: Disable the combined logging session</span></span>

```powershell
Disable-PSWSManCombinedTrace
```

## <span data-ttu-id="d7ef7-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d7ef7-112">PARAMETERS</span></span>

### <span data-ttu-id="d7ef7-113">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d7ef7-113">CommonParameters</span></span>

<span data-ttu-id="d7ef7-114">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d7ef7-114">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d7ef7-115">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d7ef7-115">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d7ef7-116">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d7ef7-116">INPUTS</span></span>

### <span data-ttu-id="d7ef7-117">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d7ef7-117">None</span></span>

## <span data-ttu-id="d7ef7-118">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d7ef7-118">OUTPUTS</span></span>

### <span data-ttu-id="d7ef7-119">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d7ef7-119">None</span></span>

## <span data-ttu-id="d7ef7-120">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d7ef7-120">NOTES</span></span>

## <span data-ttu-id="d7ef7-121">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d7ef7-121">RELATED LINKS</span></span>

[<span data-ttu-id="d7ef7-122">Rastreamento de eventos</span><span class="sxs-lookup"><span data-stu-id="d7ef7-122">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="d7ef7-123">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="d7ef7-123">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="d7ef7-124">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="d7ef7-124">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)

