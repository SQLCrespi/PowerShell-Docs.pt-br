---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-wsmantrace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManTrace
ms.openlocfilehash: a9d91eab94666186c13f8d5c928d83055f6dbefa
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598417"
---
# <span data-ttu-id="e0196-102">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="e0196-102">Enable-WSManTrace</span></span>

## <span data-ttu-id="e0196-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="e0196-103">SYNOPSIS</span></span>
<span data-ttu-id="e0196-104">Inicie uma sessão de registro em log com os provedores WSMan habilitados.</span><span class="sxs-lookup"><span data-stu-id="e0196-104">Start a logging session with the WSMan providers enabled.</span></span>

## <span data-ttu-id="e0196-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e0196-105">SYNTAX</span></span>

```
Enable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="e0196-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e0196-106">DESCRIPTION</span></span>
<span data-ttu-id="e0196-107">Este cmdlet inicia uma sessão de registro em log com os provedores WSMan habilitados.</span><span class="sxs-lookup"><span data-stu-id="e0196-107">This cmdlet starts a logging session with the WSMan providers enabled.</span></span> <span data-ttu-id="e0196-108">Os provedores de eventos a seguir estão habilitados:</span><span class="sxs-lookup"><span data-stu-id="e0196-108">The following event providers are enabled:</span></span>

- <span data-ttu-id="e0196-109">Encaminhamento de eventos</span><span class="sxs-lookup"><span data-stu-id="e0196-109">Event Forwarding</span></span>
- <span data-ttu-id="e0196-110">IpmiDrv</span><span class="sxs-lookup"><span data-stu-id="e0196-110">IpmiDrv</span></span>
- <span data-ttu-id="e0196-111">IPMIPrv</span><span class="sxs-lookup"><span data-stu-id="e0196-111">IPMIPrv</span></span>
- <span data-ttu-id="e0196-112">WinRM</span><span class="sxs-lookup"><span data-stu-id="e0196-112">WinRM</span></span>
- <span data-ttu-id="e0196-113">WinrsCmd</span><span class="sxs-lookup"><span data-stu-id="e0196-113">WinrsCmd</span></span>
- <span data-ttu-id="e0196-114">WinrsExe</span><span class="sxs-lookup"><span data-stu-id="e0196-114">WinrsExe</span></span>
- <span data-ttu-id="e0196-115">WinrsMgr</span><span class="sxs-lookup"><span data-stu-id="e0196-115">WinrsMgr</span></span>
- <span data-ttu-id="e0196-116">WSManProvHost</span><span class="sxs-lookup"><span data-stu-id="e0196-116">WSManProvHost</span></span>

<span data-ttu-id="e0196-117">A sessão é denominada ' wsmlog '.</span><span class="sxs-lookup"><span data-stu-id="e0196-117">The session is named 'wsmlog'.</span></span>

<span data-ttu-id="e0196-118">Esse cmdlet usa o `Start-Trace` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e0196-118">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="e0196-119">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="e0196-119">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="e0196-120">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e0196-120">EXAMPLES</span></span>

### <span data-ttu-id="e0196-121">Exemplo 1: iniciar uma sessão de registro em log do WSMan.</span><span class="sxs-lookup"><span data-stu-id="e0196-121">Example 1: Start a WSMan logging session.</span></span>

```powershell
Enable-WSManTrace
```

## <span data-ttu-id="e0196-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e0196-122">PARAMETERS</span></span>

### <span data-ttu-id="e0196-123">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e0196-123">CommonParameters</span></span>

<span data-ttu-id="e0196-124">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e0196-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e0196-125">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e0196-125">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e0196-126">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="e0196-126">INPUTS</span></span>

### <span data-ttu-id="e0196-127">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e0196-127">None</span></span>

## <span data-ttu-id="e0196-128">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="e0196-128">OUTPUTS</span></span>

### <span data-ttu-id="e0196-129">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e0196-129">None</span></span>

## <span data-ttu-id="e0196-130">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e0196-130">NOTES</span></span>

## <span data-ttu-id="e0196-131">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e0196-131">RELATED LINKS</span></span>

[<span data-ttu-id="e0196-132">Rastreamento de eventos</span><span class="sxs-lookup"><span data-stu-id="e0196-132">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="e0196-133">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="e0196-133">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="e0196-134">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="e0196-134">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)

