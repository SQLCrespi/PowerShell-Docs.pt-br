---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/new-winevent?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WinEvent
ms.openlocfilehash: 8605782176a96fa1901af352ceda8b453d2f1af8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194653"
---
# <span data-ttu-id="ab20f-103">New-WinEvent</span><span class="sxs-lookup"><span data-stu-id="ab20f-103">New-WinEvent</span></span>

## <span data-ttu-id="ab20f-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="ab20f-104">SYNOPSIS</span></span>
<span data-ttu-id="ab20f-105">Cria um novo evento do Windows para o provedor de eventos especificado.</span><span class="sxs-lookup"><span data-stu-id="ab20f-105">Creates a new Windows event for the specified event provider.</span></span>

## <span data-ttu-id="ab20f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ab20f-106">SYNTAX</span></span>

```
New-WinEvent [-ProviderName] <String> [-Id] <Int32> [-Version <Byte>] [[-Payload] <Object[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="ab20f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ab20f-107">DESCRIPTION</span></span>

<span data-ttu-id="ab20f-108">O **New-WinEvent** cria um evento de rastreamento de eventos do Windows (ETW) para um provedor de eventos.</span><span class="sxs-lookup"><span data-stu-id="ab20f-108">The **New-WinEvent** cmdlet creates an Event Tracing for Windows (ETW) event for an event provider.</span></span>
<span data-ttu-id="ab20f-109">Você pode usar este cmdlet para adicionar eventos a canais ETW do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab20f-109">You can use this cmdlet to add events to ETW channels from PowerShell.</span></span>

## <span data-ttu-id="ab20f-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="ab20f-110">EXAMPLES</span></span>

### <span data-ttu-id="ab20f-111">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="ab20f-111">Example 1</span></span>

```powershell
PS C:\> New-WinEvent -ProviderName Microsoft-Windows-PowerShell -Id 45090 -Payload @("Workflow", "Running")
```

<span data-ttu-id="ab20f-112">Este comando usa o cmdlet **New-WinEvent** para criar o evento 45090 para o provedor Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab20f-112">This command uses the **New-WinEvent** cmdlet to create event 45090 for the Microsoft-Windows-PowerShell provider.</span></span>

## <span data-ttu-id="ab20f-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ab20f-113">PARAMETERS</span></span>

### <span data-ttu-id="ab20f-114">-Id</span><span class="sxs-lookup"><span data-stu-id="ab20f-114">-Id</span></span>

<span data-ttu-id="ab20f-115">Especifica um identificador de evento que foi registrado por meio de um manifesto de instrumentação.</span><span class="sxs-lookup"><span data-stu-id="ab20f-115">Specifies an event id that was registered through an instrumentation manifest.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ab20f-116">-Conteúdo</span><span class="sxs-lookup"><span data-stu-id="ab20f-116">-Payload</span></span>

<span data-ttu-id="ab20f-117">Especifica a mensagem para o evento.</span><span class="sxs-lookup"><span data-stu-id="ab20f-117">Specifies the message for the event.</span></span> <span data-ttu-id="ab20f-118">Quando os eventos são gravados em um log de eventos, a carga é armazenada na propriedade **Message** do objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="ab20f-118">When the event is written to an event log, the payload is stored in the **Message** property of the event object.</span></span>

<span data-ttu-id="ab20f-119">Quando a carga especificada não corresponder à carga na definição de evento, o PowerShell gerará um aviso, mas o comando ainda terá sucesso.</span><span class="sxs-lookup"><span data-stu-id="ab20f-119">When the specified payload does not match the payload in the event definition, PowerShell generates a warning, but the command still succeeds.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ab20f-120">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="ab20f-120">-ProviderName</span></span>

<span data-ttu-id="ab20f-121">Especifica o provedor de eventos que grava o evento em um log de eventos, como "Microsoft-Windows-PowerShell".</span><span class="sxs-lookup"><span data-stu-id="ab20f-121">Specifies the event provider that writes the event to an event log, such as "Microsoft-Windows-PowerShell".</span></span> <span data-ttu-id="ab20f-122">Um provedor de eventos ETW é uma entidade lógica que grava eventos em sessões de ETW.</span><span class="sxs-lookup"><span data-stu-id="ab20f-122">An ETW event provider is a logical entity that writes events to ETW sessions.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ab20f-123">-Version</span><span class="sxs-lookup"><span data-stu-id="ab20f-123">-Version</span></span>

<span data-ttu-id="ab20f-124">Especifica o número de versão do evento.</span><span class="sxs-lookup"><span data-stu-id="ab20f-124">Specifies the version number of the event.</span></span> <span data-ttu-id="ab20f-125">Digite o número do evento.</span><span class="sxs-lookup"><span data-stu-id="ab20f-125">Type the event number.</span></span> <span data-ttu-id="ab20f-126">O PowerShell converte o número para o tipo de byte necessário.</span><span class="sxs-lookup"><span data-stu-id="ab20f-126">PowerShell converts the number to the required Byte type.</span></span>

<span data-ttu-id="ab20f-127">Este parâmetro permite que você especifique um evento quando versões diferentes do mesmo evento são definidas.</span><span class="sxs-lookup"><span data-stu-id="ab20f-127">This parameter lets you specify an event when different versions of the same event are defined.</span></span>

```yaml
Type: System.Byte
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ab20f-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ab20f-128">CommonParameters</span></span>

<span data-ttu-id="ab20f-129">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ab20f-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ab20f-130">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ab20f-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ab20f-131">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="ab20f-131">INPUTS</span></span>

### <span data-ttu-id="ab20f-132">Nenhum</span><span class="sxs-lookup"><span data-stu-id="ab20f-132">None</span></span>

<span data-ttu-id="ab20f-133">Este cmdlet não recebe entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="ab20f-133">This cmdlet does not take input from the pipeline.</span></span>

## <span data-ttu-id="ab20f-134">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="ab20f-134">OUTPUTS</span></span>

### <span data-ttu-id="ab20f-135">Nenhum</span><span class="sxs-lookup"><span data-stu-id="ab20f-135">None</span></span>

<span data-ttu-id="ab20f-136">Este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="ab20f-136">This cmdlet does to generate any output.</span></span>

## <span data-ttu-id="ab20f-137">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="ab20f-137">NOTES</span></span>

* <span data-ttu-id="ab20f-138">Depois que o provedor grava o mesmo em um EventLog, você pode usar o cmdlet Get-WinEvent para obter o evento do log de eventos.</span><span class="sxs-lookup"><span data-stu-id="ab20f-138">After the provider writes the even to an eventlog, you can use the Get-WinEvent cmdlet to get the event from the event log.</span></span>

## <span data-ttu-id="ab20f-139">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="ab20f-139">RELATED LINKS</span></span>

[<span data-ttu-id="ab20f-140">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="ab20f-140">Get-WinEvent</span></span>](Get-WinEvent.md)

