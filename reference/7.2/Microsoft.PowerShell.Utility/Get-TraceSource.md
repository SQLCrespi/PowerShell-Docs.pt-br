---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-tracesource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TraceSource
ms.openlocfilehash: c196d00359c9b20b5dc1fefc0ab2b94655703f6f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596593"
---
# <span data-ttu-id="1c248-102">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="1c248-102">Get-TraceSource</span></span>

## <span data-ttu-id="1c248-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="1c248-103">SYNOPSIS</span></span>
<span data-ttu-id="1c248-104">Obtém os componentes do PowerShell que são instrumentados para rastreamento.</span><span class="sxs-lookup"><span data-stu-id="1c248-104">Gets PowerShell components that are instrumented for tracing.</span></span>

## <span data-ttu-id="1c248-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1c248-105">SYNTAX</span></span>

```
Get-TraceSource [[-Name] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="1c248-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1c248-106">DESCRIPTION</span></span>

<span data-ttu-id="1c248-107">O cmdlet **Get-tracename** Obtém as fontes de rastreamento para os componentes do PowerShell que estão em uso no momento.</span><span class="sxs-lookup"><span data-stu-id="1c248-107">The **Get-TraceSource** cmdlet gets the trace sources for PowerShell components that are currently in use.</span></span>
<span data-ttu-id="1c248-108">Você pode usar os dados para determinar quais componentes do PowerShell você pode rastrear.</span><span class="sxs-lookup"><span data-stu-id="1c248-108">You can use the data to determine which PowerShell components you can trace.</span></span>
<span data-ttu-id="1c248-109">Ao realizar o rastreamento, o componente gera mensagens detalhadas sobre cada etapa no seu processamento interno.</span><span class="sxs-lookup"><span data-stu-id="1c248-109">When tracing, the component generates detailed messages about each step in its internal processing.</span></span>
<span data-ttu-id="1c248-110">Os desenvolvedores utilizam os dados de rastreamento para monitorar o fluxo de dados, a execução do programa e erros.</span><span class="sxs-lookup"><span data-stu-id="1c248-110">Developers use the trace data to monitor data flow, program execution, and errors.</span></span>

<span data-ttu-id="1c248-111">Os cmdlets de rastreamento foram projetados para desenvolvedores do PowerShell, mas estão disponíveis para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="1c248-111">The tracing cmdlets were designed for PowerShell developers, but they are available to all users.</span></span>

## <span data-ttu-id="1c248-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="1c248-112">EXAMPLES</span></span>

### <span data-ttu-id="1c248-113">Exemplo 1: obter fontes de rastreamento por nome</span><span class="sxs-lookup"><span data-stu-id="1c248-113">Example 1: Get trace sources by name</span></span>

```
PS C:\> Get-TraceSource -Name "*provider*"
```

<span data-ttu-id="1c248-114">Esse comando obtém todas as fontes de rastreamento que têm nomes que incluem o provedor.</span><span class="sxs-lookup"><span data-stu-id="1c248-114">This command gets all of the trace sources that have names that include provider.</span></span>

### <span data-ttu-id="1c248-115">Exemplo 2: obter todas as fontes de rastreamento</span><span class="sxs-lookup"><span data-stu-id="1c248-115">Example 2: Get all trace sources</span></span>

```
PS C:\> Get-TraceSource
```

<span data-ttu-id="1c248-116">Esse comando obtém todos os componentes do PowerShell que podem ser rastreados.</span><span class="sxs-lookup"><span data-stu-id="1c248-116">This command gets all of the PowerShell components that can be traced.</span></span>

## <span data-ttu-id="1c248-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1c248-117">PARAMETERS</span></span>

### <span data-ttu-id="1c248-118">-Name</span><span class="sxs-lookup"><span data-stu-id="1c248-118">-Name</span></span>

<span data-ttu-id="1c248-119">Especifica as origens de rastreamento a serem obtidas.</span><span class="sxs-lookup"><span data-stu-id="1c248-119">Specifies the trace sources to get.</span></span>
<span data-ttu-id="1c248-120">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="1c248-120">Wildcards are permitted.</span></span>
<span data-ttu-id="1c248-121">O *nome* do parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="1c248-121">The parameter name *Name* is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="1c248-122">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1c248-122">CommonParameters</span></span>

<span data-ttu-id="1c248-123">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1c248-123">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1c248-124">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1c248-124">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1c248-125">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="1c248-125">INPUTS</span></span>

### <span data-ttu-id="1c248-126">System.String</span><span class="sxs-lookup"><span data-stu-id="1c248-126">System.String</span></span>

<span data-ttu-id="1c248-127">É possível canalizar uma cadeia de caracteres que contém o nome de uma origem de rastreamento para **Get-tracename**.</span><span class="sxs-lookup"><span data-stu-id="1c248-127">You can pipe a string that contains the name of a trace source to **Get-TraceSource**.</span></span>

## <span data-ttu-id="1c248-128">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="1c248-128">OUTPUTS</span></span>

### <span data-ttu-id="1c248-129">System. Management. Automation. PSTraceSource</span><span class="sxs-lookup"><span data-stu-id="1c248-129">System.Management.Automation.PSTraceSource</span></span>

<span data-ttu-id="1c248-130">**Get-tracename** retorna objetos que representam as origens de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="1c248-130">**Get-TraceSource** returns objects that represent the trace sources.</span></span>

## <span data-ttu-id="1c248-131">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="1c248-131">NOTES</span></span>

## <span data-ttu-id="1c248-132">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="1c248-132">RELATED LINKS</span></span>

[<span data-ttu-id="1c248-133">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="1c248-133">Set-TraceSource</span></span>](Set-TraceSource.md)

[<span data-ttu-id="1c248-134">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="1c248-134">Trace-Command</span></span>](Trace-Command.md)

