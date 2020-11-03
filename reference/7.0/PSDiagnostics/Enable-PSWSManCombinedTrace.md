---
external help file: PSDiagnostics-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pswsmancombinedtrace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSWSManCombinedTrace
ms.openlocfilehash: f6b14ea6cda7d83792f7b51b854471a2cb62bfb5
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192735"
---
# <span data-ttu-id="35d0b-103">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="35d0b-103">Enable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="35d0b-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="35d0b-104">SYNOPSIS</span></span>
<span data-ttu-id="35d0b-105">Inicie uma sessão de registro em log com os provedores WSMan e PowerShell habilitados.</span><span class="sxs-lookup"><span data-stu-id="35d0b-105">Start a logging session with the WSMan and PowerShell providers enabled.</span></span>

## <span data-ttu-id="35d0b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="35d0b-106">SYNTAX</span></span>

```
Enable-PSWSManCombinedTrace [-DoNotOverwriteExistingTrace] [<CommonParameters>]
```

## <span data-ttu-id="35d0b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="35d0b-107">DESCRIPTION</span></span>

<span data-ttu-id="35d0b-108">Este cmdlet inicia uma sessão de log com os seguintes provedores do PowerShell habilitados:</span><span class="sxs-lookup"><span data-stu-id="35d0b-108">This cmdlet starts a logging session with the following PowerShell providers enabled:</span></span>

- <span data-ttu-id="35d0b-109">Microsoft-Windows-PowerShell</span><span class="sxs-lookup"><span data-stu-id="35d0b-109">Microsoft-Windows-PowerShell</span></span>
- <span data-ttu-id="35d0b-110">Microsoft-Windows-WinRM</span><span class="sxs-lookup"><span data-stu-id="35d0b-110">Microsoft-Windows-WinRM</span></span>

<span data-ttu-id="35d0b-111">A sessão é denominada ' PSTrace '.</span><span class="sxs-lookup"><span data-stu-id="35d0b-111">The session is named 'PSTrace'.</span></span>

<span data-ttu-id="35d0b-112">Esse cmdlet usa o `Start-Trace` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="35d0b-112">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="35d0b-113">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="35d0b-113">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="35d0b-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="35d0b-114">EXAMPLES</span></span>

### <span data-ttu-id="35d0b-115">Exemplo 1: iniciar uma sessão de registro em log combinada</span><span class="sxs-lookup"><span data-stu-id="35d0b-115">Example 1: Start a combined logging session</span></span>

```powershell
Enable-PSWSManCombinedTrace
```

## <span data-ttu-id="35d0b-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="35d0b-116">PARAMETERS</span></span>

### <span data-ttu-id="35d0b-117">-DoNotOverwriteExistingTrace</span><span class="sxs-lookup"><span data-stu-id="35d0b-117">-DoNotOverwriteExistingTrace</span></span>

<span data-ttu-id="35d0b-118">Por padrão, os eventos são gravados em "$pshome \Traces\PSTrace.etl".</span><span class="sxs-lookup"><span data-stu-id="35d0b-118">By default, the events are written to "$pshome\Traces\PSTrace.etl".</span></span> <span data-ttu-id="35d0b-119">Quando esse parâmetro é usado, o cmdlet cria um nome de arquivo exclusivo: "$pshome \Traces\ PSTrace_ {GUID}. etl"</span><span class="sxs-lookup"><span data-stu-id="35d0b-119">When this parameter is used, the cmdlet creates a unique filename: "$pshome\Traces\PSTrace_{guid}.etl"</span></span>

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

### <span data-ttu-id="35d0b-120">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="35d0b-120">CommonParameters</span></span>

<span data-ttu-id="35d0b-121">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="35d0b-121">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="35d0b-122">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="35d0b-122">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="35d0b-123">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="35d0b-123">INPUTS</span></span>

### <span data-ttu-id="35d0b-124">Nenhum</span><span class="sxs-lookup"><span data-stu-id="35d0b-124">None</span></span>

## <span data-ttu-id="35d0b-125">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="35d0b-125">OUTPUTS</span></span>

### <span data-ttu-id="35d0b-126">Nenhum</span><span class="sxs-lookup"><span data-stu-id="35d0b-126">None</span></span>

## <span data-ttu-id="35d0b-127">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="35d0b-127">NOTES</span></span>

## <span data-ttu-id="35d0b-128">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="35d0b-128">RELATED LINKS</span></span>

[<span data-ttu-id="35d0b-129">Rastreamento de eventos</span><span class="sxs-lookup"><span data-stu-id="35d0b-129">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="35d0b-130">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="35d0b-130">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="35d0b-131">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="35d0b-131">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)
