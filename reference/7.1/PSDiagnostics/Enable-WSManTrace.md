---
external help file: PSDiagnostics-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-wsmantrace?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManTrace
ms.openlocfilehash: 9a0a7f9fa81242fae10325e0c69ffc627088ae71
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "93192628"
---
# <span data-ttu-id="eb7d7-103">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="eb7d7-103">Enable-WSManTrace</span></span>

## <span data-ttu-id="eb7d7-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="eb7d7-104">SYNOPSIS</span></span>
<span data-ttu-id="eb7d7-105">Inicie uma sessão de registro em log com os provedores WSMan habilitados.</span><span class="sxs-lookup"><span data-stu-id="eb7d7-105">Start a logging session with the WSMan providers enabled.</span></span>

## <span data-ttu-id="eb7d7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="eb7d7-106">SYNTAX</span></span>

```
Enable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="eb7d7-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="eb7d7-107">DESCRIPTION</span></span>
<span data-ttu-id="eb7d7-108">Este cmdlet inicia uma sessão de registro em log com os provedores WSMan habilitados.</span><span class="sxs-lookup"><span data-stu-id="eb7d7-108">This cmdlet starts a logging session with the WSMan providers enabled.</span></span> <span data-ttu-id="eb7d7-109">Os provedores de eventos a seguir estão habilitados:</span><span class="sxs-lookup"><span data-stu-id="eb7d7-109">The following event providers are enabled:</span></span>

- <span data-ttu-id="eb7d7-110">Encaminhamento de eventos</span><span class="sxs-lookup"><span data-stu-id="eb7d7-110">Event Forwarding</span></span>
- <span data-ttu-id="eb7d7-111">IpmiDrv</span><span class="sxs-lookup"><span data-stu-id="eb7d7-111">IpmiDrv</span></span>
- <span data-ttu-id="eb7d7-112">IPMIPrv</span><span class="sxs-lookup"><span data-stu-id="eb7d7-112">IPMIPrv</span></span>
- <span data-ttu-id="eb7d7-113">WinRM</span><span class="sxs-lookup"><span data-stu-id="eb7d7-113">WinRM</span></span>
- <span data-ttu-id="eb7d7-114">WinrsCmd</span><span class="sxs-lookup"><span data-stu-id="eb7d7-114">WinrsCmd</span></span>
- <span data-ttu-id="eb7d7-115">WinrsExe</span><span class="sxs-lookup"><span data-stu-id="eb7d7-115">WinrsExe</span></span>
- <span data-ttu-id="eb7d7-116">WinrsMgr</span><span class="sxs-lookup"><span data-stu-id="eb7d7-116">WinrsMgr</span></span>
- <span data-ttu-id="eb7d7-117">WSManProvHost</span><span class="sxs-lookup"><span data-stu-id="eb7d7-117">WSManProvHost</span></span>

<span data-ttu-id="eb7d7-118">A sessão é denominada ' wsmlog '.</span><span class="sxs-lookup"><span data-stu-id="eb7d7-118">The session is named 'wsmlog'.</span></span>

<span data-ttu-id="eb7d7-119">Esse cmdlet usa o `Start-Trace` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eb7d7-119">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="eb7d7-120">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="eb7d7-120">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="eb7d7-121">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="eb7d7-121">EXAMPLES</span></span>

### <span data-ttu-id="eb7d7-122">Exemplo 1: iniciar uma sessão de registro em log do WSMan.</span><span class="sxs-lookup"><span data-stu-id="eb7d7-122">Example 1: Start a WSMan logging session.</span></span>

```powershell
Enable-WSManTrace
```

## <span data-ttu-id="eb7d7-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="eb7d7-123">PARAMETERS</span></span>

### <span data-ttu-id="eb7d7-124">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="eb7d7-124">CommonParameters</span></span>

<span data-ttu-id="eb7d7-125">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="eb7d7-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="eb7d7-126">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="eb7d7-126">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="eb7d7-127">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="eb7d7-127">INPUTS</span></span>

### <span data-ttu-id="eb7d7-128">Nenhum</span><span class="sxs-lookup"><span data-stu-id="eb7d7-128">None</span></span>

## <span data-ttu-id="eb7d7-129">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="eb7d7-129">OUTPUTS</span></span>

### <span data-ttu-id="eb7d7-130">Nenhum</span><span class="sxs-lookup"><span data-stu-id="eb7d7-130">None</span></span>

## <span data-ttu-id="eb7d7-131">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="eb7d7-131">NOTES</span></span>

## <span data-ttu-id="eb7d7-132">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="eb7d7-132">RELATED LINKS</span></span>

[<span data-ttu-id="eb7d7-133">Rastreamento de eventos</span><span class="sxs-lookup"><span data-stu-id="eb7d7-133">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="eb7d7-134">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="eb7d7-134">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="eb7d7-135">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="eb7d7-135">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)

