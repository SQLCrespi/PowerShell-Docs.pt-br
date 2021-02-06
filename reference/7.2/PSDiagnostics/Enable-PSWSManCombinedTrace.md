---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pswsmancombinedtrace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSWSManCombinedTrace
ms.openlocfilehash: ef333edaa091e96df11a8288e9b16f133614c1e0
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603346"
---
# <span data-ttu-id="f705a-102">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="f705a-102">Enable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="f705a-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="f705a-103">SYNOPSIS</span></span>
<span data-ttu-id="f705a-104">Inicie uma sessão de registro em log com os provedores WSMan e PowerShell habilitados.</span><span class="sxs-lookup"><span data-stu-id="f705a-104">Start a logging session with the WSMan and PowerShell providers enabled.</span></span>

## <span data-ttu-id="f705a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f705a-105">SYNTAX</span></span>

```
Enable-PSWSManCombinedTrace [-DoNotOverwriteExistingTrace] [<CommonParameters>]
```

## <span data-ttu-id="f705a-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f705a-106">DESCRIPTION</span></span>

<span data-ttu-id="f705a-107">Este cmdlet inicia uma sessão de log com os seguintes provedores do PowerShell habilitados:</span><span class="sxs-lookup"><span data-stu-id="f705a-107">This cmdlet starts a logging session with the following PowerShell providers enabled:</span></span>

- <span data-ttu-id="f705a-108">Microsoft-Windows-PowerShell</span><span class="sxs-lookup"><span data-stu-id="f705a-108">Microsoft-Windows-PowerShell</span></span>
- <span data-ttu-id="f705a-109">Microsoft-Windows-WinRM</span><span class="sxs-lookup"><span data-stu-id="f705a-109">Microsoft-Windows-WinRM</span></span>

<span data-ttu-id="f705a-110">A sessão é denominada ' PSTrace '.</span><span class="sxs-lookup"><span data-stu-id="f705a-110">The session is named 'PSTrace'.</span></span>

<span data-ttu-id="f705a-111">Esse cmdlet usa o `Start-Trace` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f705a-111">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="f705a-112">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="f705a-112">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="f705a-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="f705a-113">EXAMPLES</span></span>

### <span data-ttu-id="f705a-114">Exemplo 1: iniciar uma sessão de registro em log combinada</span><span class="sxs-lookup"><span data-stu-id="f705a-114">Example 1: Start a combined logging session</span></span>

```powershell
Enable-PSWSManCombinedTrace
```

## <span data-ttu-id="f705a-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f705a-115">PARAMETERS</span></span>

### <span data-ttu-id="f705a-116">-DoNotOverwriteExistingTrace</span><span class="sxs-lookup"><span data-stu-id="f705a-116">-DoNotOverwriteExistingTrace</span></span>

<span data-ttu-id="f705a-117">Por padrão, os eventos são gravados em "$pshome \Traces\PSTrace.etl".</span><span class="sxs-lookup"><span data-stu-id="f705a-117">By default, the events are written to "$pshome\Traces\PSTrace.etl".</span></span> <span data-ttu-id="f705a-118">Quando esse parâmetro é usado, o cmdlet cria um nome de arquivo exclusivo: "$pshome \Traces\ PSTrace_ {GUID}. etl"</span><span class="sxs-lookup"><span data-stu-id="f705a-118">When this parameter is used, the cmdlet creates a unique filename: "$pshome\Traces\PSTrace_{guid}.etl"</span></span>

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

### <span data-ttu-id="f705a-119">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f705a-119">CommonParameters</span></span>

<span data-ttu-id="f705a-120">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f705a-120">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f705a-121">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f705a-121">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f705a-122">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="f705a-122">INPUTS</span></span>

### <span data-ttu-id="f705a-123">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f705a-123">None</span></span>

## <span data-ttu-id="f705a-124">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="f705a-124">OUTPUTS</span></span>

### <span data-ttu-id="f705a-125">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f705a-125">None</span></span>

## <span data-ttu-id="f705a-126">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="f705a-126">NOTES</span></span>

## <span data-ttu-id="f705a-127">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f705a-127">RELATED LINKS</span></span>

[<span data-ttu-id="f705a-128">Rastreamento de eventos</span><span class="sxs-lookup"><span data-stu-id="f705a-128">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="f705a-129">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="f705a-129">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="f705a-130">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="f705a-130">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

