---
external help file: PSDiagnostics-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pswsmancombinedtrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSWSManCombinedTrace
ms.openlocfilehash: f67b5d9fe8da48cca5fd4ec7d2056a4702d3ff16
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193701"
---
# <span data-ttu-id="44d04-103">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="44d04-103">Enable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="44d04-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="44d04-104">SYNOPSIS</span></span>
<span data-ttu-id="44d04-105">Inicie uma sessão de registro em log com os provedores WSMan e PowerShell habilitados.</span><span class="sxs-lookup"><span data-stu-id="44d04-105">Start a logging session with the WSMan and PowerShell providers enabled.</span></span>

## <span data-ttu-id="44d04-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="44d04-106">SYNTAX</span></span>

```
Enable-PSWSManCombinedTrace [-DoNotOverwriteExistingTrace] [<CommonParameters>]
```

## <span data-ttu-id="44d04-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="44d04-107">DESCRIPTION</span></span>

<span data-ttu-id="44d04-108">Este cmdlet inicia uma sessão de log com os seguintes provedores do PowerShell habilitados:</span><span class="sxs-lookup"><span data-stu-id="44d04-108">This cmdlet starts a logging session with the following PowerShell providers enabled:</span></span>

- <span data-ttu-id="44d04-109">Microsoft-Windows-PowerShell</span><span class="sxs-lookup"><span data-stu-id="44d04-109">Microsoft-Windows-PowerShell</span></span>
- <span data-ttu-id="44d04-110">Microsoft-Windows-WinRM</span><span class="sxs-lookup"><span data-stu-id="44d04-110">Microsoft-Windows-WinRM</span></span>

<span data-ttu-id="44d04-111">A sessão é denominada ' PSTrace '.</span><span class="sxs-lookup"><span data-stu-id="44d04-111">The session is named 'PSTrace'.</span></span>

<span data-ttu-id="44d04-112">Esse cmdlet usa o `Start-Trace` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="44d04-112">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="44d04-113">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="44d04-113">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="44d04-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="44d04-114">EXAMPLES</span></span>

### <span data-ttu-id="44d04-115">Exemplo 1: iniciar uma sessão de registro em log combinada</span><span class="sxs-lookup"><span data-stu-id="44d04-115">Example 1: Start a combined logging session</span></span>

```powershell
Enable-PSWSManCombinedTrace
```

## <span data-ttu-id="44d04-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="44d04-116">PARAMETERS</span></span>

### <span data-ttu-id="44d04-117">-DoNotOverwriteExistingTrace</span><span class="sxs-lookup"><span data-stu-id="44d04-117">-DoNotOverwriteExistingTrace</span></span>

<span data-ttu-id="44d04-118">Por padrão, os eventos são gravados em "$pshome \Traces\PSTrace.etl".</span><span class="sxs-lookup"><span data-stu-id="44d04-118">By default, the events are written to "$pshome\Traces\PSTrace.etl".</span></span> <span data-ttu-id="44d04-119">Quando esse parâmetro é usado, o cmdlet cria um nome de arquivo exclusivo: "$pshome \Traces\ PSTrace_ {GUID}. etl"</span><span class="sxs-lookup"><span data-stu-id="44d04-119">When this parameter is used, the cmdlet creates a unique filename: "$pshome\Traces\PSTrace_{guid}.etl"</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="44d04-120">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="44d04-120">CommonParameters</span></span>

<span data-ttu-id="44d04-121">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="44d04-121">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="44d04-122">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="44d04-122">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="44d04-123">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="44d04-123">INPUTS</span></span>

### <span data-ttu-id="44d04-124">Nenhum</span><span class="sxs-lookup"><span data-stu-id="44d04-124">None</span></span>

## <span data-ttu-id="44d04-125">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="44d04-125">OUTPUTS</span></span>

### <span data-ttu-id="44d04-126">System.Object</span><span class="sxs-lookup"><span data-stu-id="44d04-126">System.Object</span></span>

## <span data-ttu-id="44d04-127">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="44d04-127">NOTES</span></span>

## <span data-ttu-id="44d04-128">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="44d04-128">RELATED LINKS</span></span>

[<span data-ttu-id="44d04-129">Rastreamento de eventos</span><span class="sxs-lookup"><span data-stu-id="44d04-129">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="44d04-130">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="44d04-130">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="44d04-131">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="44d04-131">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)
