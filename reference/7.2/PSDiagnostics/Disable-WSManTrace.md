---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-wsmantrace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManTrace
ms.openlocfilehash: 647a7676eddf2175bf29e02b3482cc9c7c4d8ebe
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596786"
---
# <span data-ttu-id="f18e0-102">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="f18e0-102">Disable-WSManTrace</span></span>

## <span data-ttu-id="f18e0-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="f18e0-103">SYNOPSIS</span></span>
<span data-ttu-id="f18e0-104">Pare a sessão de registro em log do WSMan iniciada por Enable-WSManTrace.</span><span class="sxs-lookup"><span data-stu-id="f18e0-104">Stop the WSMan logging session started by Enable-WSManTrace.</span></span>

## <span data-ttu-id="f18e0-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f18e0-105">SYNTAX</span></span>

```
Disable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="f18e0-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f18e0-106">DESCRIPTION</span></span>
<span data-ttu-id="f18e0-107">Esse cmdlet interrompe a sessão de registro em log do WSMan iniciada por Enable-WSManTrace.</span><span class="sxs-lookup"><span data-stu-id="f18e0-107">This cmdlet stops the WSMan logging session started by Enable-WSManTrace.</span></span>

<span data-ttu-id="f18e0-108">Esse cmdlet usa o `Stop-Trace` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f18e0-108">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="f18e0-109">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="f18e0-109">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="f18e0-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="f18e0-110">EXAMPLES</span></span>

### <span data-ttu-id="f18e0-111">Exemplo 1: parar um rastreamento WSMan</span><span class="sxs-lookup"><span data-stu-id="f18e0-111">Example 1: Stop a WSMan trace</span></span>

```powershell
Disable-WSManTrace
```

## <span data-ttu-id="f18e0-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f18e0-112">PARAMETERS</span></span>

### <span data-ttu-id="f18e0-113">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f18e0-113">CommonParameters</span></span>

<span data-ttu-id="f18e0-114">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f18e0-114">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f18e0-115">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f18e0-115">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f18e0-116">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="f18e0-116">INPUTS</span></span>

### <span data-ttu-id="f18e0-117">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f18e0-117">None</span></span>

## <span data-ttu-id="f18e0-118">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="f18e0-118">OUTPUTS</span></span>

### <span data-ttu-id="f18e0-119">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f18e0-119">None</span></span>

## <span data-ttu-id="f18e0-120">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="f18e0-120">NOTES</span></span>

## <span data-ttu-id="f18e0-121">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f18e0-121">RELATED LINKS</span></span>

[<span data-ttu-id="f18e0-122">Rastreamento de eventos</span><span class="sxs-lookup"><span data-stu-id="f18e0-122">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="f18e0-123">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="f18e0-123">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="f18e0-124">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="f18e0-124">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)

