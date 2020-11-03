---
external help file: PSDiagnostics-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pswsmancombinedtrace?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSWSManCombinedTrace
ms.openlocfilehash: cfe73dea98cdf858f1364e1daf434334b57a62cd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194587"
---
# <span data-ttu-id="99f82-103">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="99f82-103">Enable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="99f82-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="99f82-104">SYNOPSIS</span></span>
<span data-ttu-id="99f82-105">Inicie uma sessão de registro em log com os provedores WSMan e PowerShell habilitados.</span><span class="sxs-lookup"><span data-stu-id="99f82-105">Start a logging session with the WSMan and PowerShell providers enabled.</span></span>

## <span data-ttu-id="99f82-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="99f82-106">SYNTAX</span></span>

```
Enable-PSWSManCombinedTrace [-DoNotOverwriteExistingTrace] [<CommonParameters>]
```

## <span data-ttu-id="99f82-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="99f82-107">DESCRIPTION</span></span>

<span data-ttu-id="99f82-108">Este cmdlet inicia uma sessão de log com os seguintes provedores do PowerShell habilitados:</span><span class="sxs-lookup"><span data-stu-id="99f82-108">This cmdlet starts a logging session with the following PowerShell providers enabled:</span></span>

- <span data-ttu-id="99f82-109">Microsoft-Windows-PowerShell</span><span class="sxs-lookup"><span data-stu-id="99f82-109">Microsoft-Windows-PowerShell</span></span>
- <span data-ttu-id="99f82-110">Microsoft-Windows-WinRM</span><span class="sxs-lookup"><span data-stu-id="99f82-110">Microsoft-Windows-WinRM</span></span>

<span data-ttu-id="99f82-111">A sessão é denominada ' PSTrace '.</span><span class="sxs-lookup"><span data-stu-id="99f82-111">The session is named 'PSTrace'.</span></span>

<span data-ttu-id="99f82-112">Esse cmdlet usa o `Start-Trace` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="99f82-112">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="99f82-113">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="99f82-113">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="99f82-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="99f82-114">EXAMPLES</span></span>

### <span data-ttu-id="99f82-115">Exemplo 1: iniciar uma sessão de registro em log combinada</span><span class="sxs-lookup"><span data-stu-id="99f82-115">Example 1: Start a combined logging session</span></span>

```powershell
Enable-PSWSManCombinedTrace
```

## <span data-ttu-id="99f82-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="99f82-116">PARAMETERS</span></span>

### <span data-ttu-id="99f82-117">-DoNotOverwriteExistingTrace</span><span class="sxs-lookup"><span data-stu-id="99f82-117">-DoNotOverwriteExistingTrace</span></span>

<span data-ttu-id="99f82-118">Por padrão, os eventos são gravados em "$pshome \Traces\PSTrace.etl".</span><span class="sxs-lookup"><span data-stu-id="99f82-118">By default, the events are written to "$pshome\Traces\PSTrace.etl".</span></span> <span data-ttu-id="99f82-119">Quando esse parâmetro é usado, o cmdlet cria um nome de arquivo exclusivo: "$pshome \Traces\ PSTrace_ {GUID}. etl"</span><span class="sxs-lookup"><span data-stu-id="99f82-119">When this parameter is used, the cmdlet creates a unique filename: "$pshome\Traces\PSTrace_{guid}.etl"</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99f82-120">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="99f82-120">CommonParameters</span></span>

<span data-ttu-id="99f82-121">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="99f82-121">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="99f82-122">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="99f82-122">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="99f82-123">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="99f82-123">INPUTS</span></span>

### <span data-ttu-id="99f82-124">Nenhum</span><span class="sxs-lookup"><span data-stu-id="99f82-124">None</span></span>

## <span data-ttu-id="99f82-125">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="99f82-125">OUTPUTS</span></span>

### <span data-ttu-id="99f82-126">Nenhum</span><span class="sxs-lookup"><span data-stu-id="99f82-126">None</span></span>

## <span data-ttu-id="99f82-127">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="99f82-127">NOTES</span></span>

## <span data-ttu-id="99f82-128">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="99f82-128">RELATED LINKS</span></span>

[<span data-ttu-id="99f82-129">Rastreamento de eventos</span><span class="sxs-lookup"><span data-stu-id="99f82-129">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="99f82-130">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="99f82-130">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="99f82-131">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="99f82-131">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)
