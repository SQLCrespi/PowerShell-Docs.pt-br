---
external help file: PSDiagnostics-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-wsmantrace?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManTrace
ms.openlocfilehash: 70ce4849e78262fc3553502d307e1df4e9ecfcf3
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "93192605"
---
# <span data-ttu-id="72108-103">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="72108-103">Enable-WSManTrace</span></span>

## <span data-ttu-id="72108-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="72108-104">SYNOPSIS</span></span>
<span data-ttu-id="72108-105">Inicie uma sessão de registro em log com os provedores WSMan habilitados.</span><span class="sxs-lookup"><span data-stu-id="72108-105">Start a logging session with the WSMan providers enabled.</span></span>

## <span data-ttu-id="72108-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="72108-106">SYNTAX</span></span>

```
Enable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="72108-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="72108-107">DESCRIPTION</span></span>
<span data-ttu-id="72108-108">Este cmdlet inicia uma sessão de registro em log com os provedores WSMan habilitados.</span><span class="sxs-lookup"><span data-stu-id="72108-108">This cmdlet starts a logging session with the WSMan providers enabled.</span></span> <span data-ttu-id="72108-109">Os provedores de eventos a seguir estão habilitados:</span><span class="sxs-lookup"><span data-stu-id="72108-109">The following event providers are enabled:</span></span>

- <span data-ttu-id="72108-110">Encaminhamento de eventos</span><span class="sxs-lookup"><span data-stu-id="72108-110">Event Forwarding</span></span>
- <span data-ttu-id="72108-111">IpmiDrv</span><span class="sxs-lookup"><span data-stu-id="72108-111">IpmiDrv</span></span>
- <span data-ttu-id="72108-112">IPMIPrv</span><span class="sxs-lookup"><span data-stu-id="72108-112">IPMIPrv</span></span>
- <span data-ttu-id="72108-113">WinRM</span><span class="sxs-lookup"><span data-stu-id="72108-113">WinRM</span></span>
- <span data-ttu-id="72108-114">WinrsCmd</span><span class="sxs-lookup"><span data-stu-id="72108-114">WinrsCmd</span></span>
- <span data-ttu-id="72108-115">WinrsExe</span><span class="sxs-lookup"><span data-stu-id="72108-115">WinrsExe</span></span>
- <span data-ttu-id="72108-116">WinrsMgr</span><span class="sxs-lookup"><span data-stu-id="72108-116">WinrsMgr</span></span>
- <span data-ttu-id="72108-117">WSManProvHost</span><span class="sxs-lookup"><span data-stu-id="72108-117">WSManProvHost</span></span>

<span data-ttu-id="72108-118">A sessão é denominada ' wsmlog '.</span><span class="sxs-lookup"><span data-stu-id="72108-118">The session is named 'wsmlog'.</span></span>

<span data-ttu-id="72108-119">Esse cmdlet usa o `Start-Trace` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="72108-119">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="72108-120">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="72108-120">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="72108-121">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="72108-121">EXAMPLES</span></span>

### <span data-ttu-id="72108-122">Exemplo 1: iniciar uma sessão de registro em log do WSMan.</span><span class="sxs-lookup"><span data-stu-id="72108-122">Example 1: Start a WSMan logging session.</span></span>

```powershell
Enable-WSManTrace
```

## <span data-ttu-id="72108-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="72108-123">PARAMETERS</span></span>

### <span data-ttu-id="72108-124">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="72108-124">CommonParameters</span></span>

<span data-ttu-id="72108-125">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="72108-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="72108-126">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="72108-126">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="72108-127">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="72108-127">INPUTS</span></span>

### <span data-ttu-id="72108-128">Nenhum</span><span class="sxs-lookup"><span data-stu-id="72108-128">None</span></span>

## <span data-ttu-id="72108-129">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="72108-129">OUTPUTS</span></span>

### <span data-ttu-id="72108-130">Nenhum</span><span class="sxs-lookup"><span data-stu-id="72108-130">None</span></span>

## <span data-ttu-id="72108-131">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="72108-131">NOTES</span></span>

## <span data-ttu-id="72108-132">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="72108-132">RELATED LINKS</span></span>

[<span data-ttu-id="72108-133">Rastreamento de eventos</span><span class="sxs-lookup"><span data-stu-id="72108-133">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="72108-134">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="72108-134">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="72108-135">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="72108-135">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)
