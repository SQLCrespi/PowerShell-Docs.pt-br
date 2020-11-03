---
external help file: PSDiagnostics-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-wsmantrace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManTrace
ms.openlocfilehash: c872b57186a854a67908bb07daac7f1a31bbb995
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "93192655"
---
# <span data-ttu-id="c1a48-103">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="c1a48-103">Enable-WSManTrace</span></span>

## <span data-ttu-id="c1a48-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="c1a48-104">SYNOPSIS</span></span>
<span data-ttu-id="c1a48-105">Inicie uma sessão de registro em log com os provedores WSMan habilitados.</span><span class="sxs-lookup"><span data-stu-id="c1a48-105">Start a logging session with the WSMan providers enabled.</span></span>

## <span data-ttu-id="c1a48-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c1a48-106">SYNTAX</span></span>

```
Enable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="c1a48-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c1a48-107">DESCRIPTION</span></span>
<span data-ttu-id="c1a48-108">Este cmdlet inicia uma sessão de registro em log com os provedores WSMan habilitados.</span><span class="sxs-lookup"><span data-stu-id="c1a48-108">This cmdlet starts a logging session with the WSMan providers enabled.</span></span> <span data-ttu-id="c1a48-109">Os provedores de eventos a seguir estão habilitados:</span><span class="sxs-lookup"><span data-stu-id="c1a48-109">The following event providers are enabled:</span></span>

- <span data-ttu-id="c1a48-110">Encaminhamento de eventos</span><span class="sxs-lookup"><span data-stu-id="c1a48-110">Event Forwarding</span></span>
- <span data-ttu-id="c1a48-111">IpmiDrv</span><span class="sxs-lookup"><span data-stu-id="c1a48-111">IpmiDrv</span></span>
- <span data-ttu-id="c1a48-112">IPMIPrv</span><span class="sxs-lookup"><span data-stu-id="c1a48-112">IPMIPrv</span></span>
- <span data-ttu-id="c1a48-113">WinRM</span><span class="sxs-lookup"><span data-stu-id="c1a48-113">WinRM</span></span>
- <span data-ttu-id="c1a48-114">WinrsCmd</span><span class="sxs-lookup"><span data-stu-id="c1a48-114">WinrsCmd</span></span>
- <span data-ttu-id="c1a48-115">WinrsExe</span><span class="sxs-lookup"><span data-stu-id="c1a48-115">WinrsExe</span></span>
- <span data-ttu-id="c1a48-116">WinrsMgr</span><span class="sxs-lookup"><span data-stu-id="c1a48-116">WinrsMgr</span></span>
- <span data-ttu-id="c1a48-117">WSManProvHost</span><span class="sxs-lookup"><span data-stu-id="c1a48-117">WSManProvHost</span></span>

<span data-ttu-id="c1a48-118">A sessão é denominada ' wsmlog '.</span><span class="sxs-lookup"><span data-stu-id="c1a48-118">The session is named 'wsmlog'.</span></span>

<span data-ttu-id="c1a48-119">Esse cmdlet usa o `Start-Trace` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c1a48-119">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="c1a48-120">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="c1a48-120">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="c1a48-121">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="c1a48-121">EXAMPLES</span></span>

### <span data-ttu-id="c1a48-122">Exemplo 1: iniciar uma sessão de registro em log do WSMan.</span><span class="sxs-lookup"><span data-stu-id="c1a48-122">Example 1: Start a WSMan logging session.</span></span>

```powershell
Enable-WSManTrace
```

## <span data-ttu-id="c1a48-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c1a48-123">PARAMETERS</span></span>

### <span data-ttu-id="c1a48-124">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c1a48-124">CommonParameters</span></span>

<span data-ttu-id="c1a48-125">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c1a48-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c1a48-126">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c1a48-126">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c1a48-127">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="c1a48-127">INPUTS</span></span>

### <span data-ttu-id="c1a48-128">Nenhum</span><span class="sxs-lookup"><span data-stu-id="c1a48-128">None</span></span>

## <span data-ttu-id="c1a48-129">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="c1a48-129">OUTPUTS</span></span>

### <span data-ttu-id="c1a48-130">Nenhum</span><span class="sxs-lookup"><span data-stu-id="c1a48-130">None</span></span>

## <span data-ttu-id="c1a48-131">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="c1a48-131">NOTES</span></span>

## <span data-ttu-id="c1a48-132">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="c1a48-132">RELATED LINKS</span></span>

[<span data-ttu-id="c1a48-133">Rastreamento de eventos</span><span class="sxs-lookup"><span data-stu-id="c1a48-133">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="c1a48-134">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="c1a48-134">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="c1a48-135">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="c1a48-135">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)
