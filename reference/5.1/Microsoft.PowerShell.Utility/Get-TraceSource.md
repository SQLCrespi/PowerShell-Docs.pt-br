---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-tracesource?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TraceSource
ms.openlocfilehash: 7d57e7cff0dc3ca0eff36dbe38e240efdd324060
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193799"
---
# <span data-ttu-id="f3371-103">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="f3371-103">Get-TraceSource</span></span>

## <span data-ttu-id="f3371-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="f3371-104">SYNOPSIS</span></span>
<span data-ttu-id="f3371-105">Obtém os componentes do PowerShell que são instrumentados para rastreamento.</span><span class="sxs-lookup"><span data-stu-id="f3371-105">Gets PowerShell components that are instrumented for tracing.</span></span>

## <span data-ttu-id="f3371-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f3371-106">SYNTAX</span></span>

```
Get-TraceSource [[-Name] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="f3371-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f3371-107">DESCRIPTION</span></span>

<span data-ttu-id="f3371-108">O cmdlet **Get-tracename** Obtém as fontes de rastreamento para os componentes do PowerShell que estão em uso no momento.</span><span class="sxs-lookup"><span data-stu-id="f3371-108">The **Get-TraceSource** cmdlet gets the trace sources for PowerShell components that are currently in use.</span></span>
<span data-ttu-id="f3371-109">Você pode usar os dados para determinar quais componentes do PowerShell você pode rastrear.</span><span class="sxs-lookup"><span data-stu-id="f3371-109">You can use the data to determine which PowerShell components you can trace.</span></span>
<span data-ttu-id="f3371-110">Ao realizar o rastreamento, o componente gera mensagens detalhadas sobre cada etapa no seu processamento interno.</span><span class="sxs-lookup"><span data-stu-id="f3371-110">When tracing, the component generates detailed messages about each step in its internal processing.</span></span>
<span data-ttu-id="f3371-111">Os desenvolvedores utilizam os dados de rastreamento para monitorar o fluxo de dados, a execução do programa e erros.</span><span class="sxs-lookup"><span data-stu-id="f3371-111">Developers use the trace data to monitor data flow, program execution, and errors.</span></span>

<span data-ttu-id="f3371-112">Os cmdlets de rastreamento foram projetados para desenvolvedores do PowerShell, mas estão disponíveis para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="f3371-112">The tracing cmdlets were designed for PowerShell developers, but they are available to all users.</span></span>

## <span data-ttu-id="f3371-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="f3371-113">EXAMPLES</span></span>

### <span data-ttu-id="f3371-114">Exemplo 1: obter fontes de rastreamento por nome</span><span class="sxs-lookup"><span data-stu-id="f3371-114">Example 1: Get trace sources by name</span></span>

```
PS C:\> Get-TraceSource -Name "*provider*"
```

<span data-ttu-id="f3371-115">Esse comando obtém todas as fontes de rastreamento que têm nomes que incluem o provedor.</span><span class="sxs-lookup"><span data-stu-id="f3371-115">This command gets all of the trace sources that have names that include provider.</span></span>

### <span data-ttu-id="f3371-116">Exemplo 2: obter todas as fontes de rastreamento</span><span class="sxs-lookup"><span data-stu-id="f3371-116">Example 2: Get all trace sources</span></span>

```
PS C:\> Get-TraceSource
```

<span data-ttu-id="f3371-117">Esse comando obtém todos os componentes do PowerShell que podem ser rastreados.</span><span class="sxs-lookup"><span data-stu-id="f3371-117">This command gets all of the PowerShell components that can be traced.</span></span>

## <span data-ttu-id="f3371-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f3371-118">PARAMETERS</span></span>

### <span data-ttu-id="f3371-119">-Name</span><span class="sxs-lookup"><span data-stu-id="f3371-119">-Name</span></span>

<span data-ttu-id="f3371-120">Especifica as origens de rastreamento a serem obtidas.</span><span class="sxs-lookup"><span data-stu-id="f3371-120">Specifies the trace sources to get.</span></span>
<span data-ttu-id="f3371-121">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="f3371-121">Wildcards are permitted.</span></span>
<span data-ttu-id="f3371-122">O *nome* do parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="f3371-122">The parameter name *Name* is optional.</span></span>

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

### <span data-ttu-id="f3371-123">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f3371-123">CommonParameters</span></span>

<span data-ttu-id="f3371-124">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f3371-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f3371-125">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f3371-125">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f3371-126">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="f3371-126">INPUTS</span></span>

### <span data-ttu-id="f3371-127">System.String</span><span class="sxs-lookup"><span data-stu-id="f3371-127">System.String</span></span>

<span data-ttu-id="f3371-128">É possível canalizar uma cadeia de caracteres que contém o nome de uma origem de rastreamento para **Get-tracename** .</span><span class="sxs-lookup"><span data-stu-id="f3371-128">You can pipe a string that contains the name of a trace source to **Get-TraceSource** .</span></span>

## <span data-ttu-id="f3371-129">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="f3371-129">OUTPUTS</span></span>

### <span data-ttu-id="f3371-130">System. Management. Automation. PSTraceSource</span><span class="sxs-lookup"><span data-stu-id="f3371-130">System.Management.Automation.PSTraceSource</span></span>

<span data-ttu-id="f3371-131">**Get-tracename** retorna objetos que representam as origens de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="f3371-131">**Get-TraceSource** returns objects that represent the trace sources.</span></span>

## <span data-ttu-id="f3371-132">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="f3371-132">NOTES</span></span>

## <span data-ttu-id="f3371-133">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f3371-133">RELATED LINKS</span></span>

[<span data-ttu-id="f3371-134">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="f3371-134">Set-TraceSource</span></span>](Set-TraceSource.md)

[<span data-ttu-id="f3371-135">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="f3371-135">Trace-Command</span></span>](Trace-Command.md)
