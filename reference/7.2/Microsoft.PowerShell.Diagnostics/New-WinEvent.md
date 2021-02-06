---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/new-winevent?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WinEvent
ms.openlocfilehash: 5b4b150a1c02e5d0689b44db9b2a984e297db766
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596810"
---
# <span data-ttu-id="b5089-102">New-WinEvent</span><span class="sxs-lookup"><span data-stu-id="b5089-102">New-WinEvent</span></span>

## <span data-ttu-id="b5089-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b5089-103">SYNOPSIS</span></span>
<span data-ttu-id="b5089-104">Cria um novo evento do Windows para o provedor de eventos especificado.</span><span class="sxs-lookup"><span data-stu-id="b5089-104">Creates a new Windows event for the specified event provider.</span></span>

## <span data-ttu-id="b5089-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b5089-105">SYNTAX</span></span>

```
New-WinEvent [-ProviderName] <String> [-Id] <Int32> [-Version <Byte>] [[-Payload] <Object[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="b5089-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b5089-106">DESCRIPTION</span></span>

<span data-ttu-id="b5089-107">O **New-WinEvent** cria um evento de rastreamento de eventos do Windows (ETW) para um provedor de eventos.</span><span class="sxs-lookup"><span data-stu-id="b5089-107">The **New-WinEvent** cmdlet creates an Event Tracing for Windows (ETW) event for an event provider.</span></span>
<span data-ttu-id="b5089-108">Você pode usar este cmdlet para adicionar eventos a canais ETW do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b5089-108">You can use this cmdlet to add events to ETW channels from PowerShell.</span></span>

## <span data-ttu-id="b5089-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b5089-109">EXAMPLES</span></span>

### <span data-ttu-id="b5089-110">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="b5089-110">Example 1</span></span>

```powershell
PS C:\> New-WinEvent -ProviderName Microsoft-Windows-PowerShell -Id 45090 -Payload @("Workflow", "Running")
```

<span data-ttu-id="b5089-111">Este comando usa o cmdlet **New-WinEvent** para criar o evento 45090 para o provedor Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b5089-111">This command uses the **New-WinEvent** cmdlet to create event 45090 for the Microsoft-Windows-PowerShell provider.</span></span>

## <span data-ttu-id="b5089-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b5089-112">PARAMETERS</span></span>

### <span data-ttu-id="b5089-113">-Id</span><span class="sxs-lookup"><span data-stu-id="b5089-113">-Id</span></span>

<span data-ttu-id="b5089-114">Especifica um identificador de evento que foi registrado por meio de um manifesto de instrumentação.</span><span class="sxs-lookup"><span data-stu-id="b5089-114">Specifies an event id that was registered through an instrumentation manifest.</span></span>

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

### <span data-ttu-id="b5089-115">-Conteúdo</span><span class="sxs-lookup"><span data-stu-id="b5089-115">-Payload</span></span>

<span data-ttu-id="b5089-116">Especifica a mensagem para o evento.</span><span class="sxs-lookup"><span data-stu-id="b5089-116">Specifies the message for the event.</span></span> <span data-ttu-id="b5089-117">Quando os eventos são gravados em um log de eventos, a carga é armazenada na propriedade **Message** do objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="b5089-117">When the event is written to an event log, the payload is stored in the **Message** property of the event object.</span></span>

<span data-ttu-id="b5089-118">Quando a carga especificada não corresponder à carga na definição de evento, o PowerShell gerará um aviso, mas o comando ainda terá sucesso.</span><span class="sxs-lookup"><span data-stu-id="b5089-118">When the specified payload does not match the payload in the event definition, PowerShell generates a warning, but the command still succeeds.</span></span>

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

### <span data-ttu-id="b5089-119">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="b5089-119">-ProviderName</span></span>

<span data-ttu-id="b5089-120">Especifica o provedor de eventos que grava o evento em um log de eventos, como "Microsoft-Windows-PowerShell".</span><span class="sxs-lookup"><span data-stu-id="b5089-120">Specifies the event provider that writes the event to an event log, such as "Microsoft-Windows-PowerShell".</span></span> <span data-ttu-id="b5089-121">Um provedor de eventos ETW é uma entidade lógica que grava eventos em sessões de ETW.</span><span class="sxs-lookup"><span data-stu-id="b5089-121">An ETW event provider is a logical entity that writes events to ETW sessions.</span></span>

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

### <span data-ttu-id="b5089-122">-Version</span><span class="sxs-lookup"><span data-stu-id="b5089-122">-Version</span></span>

<span data-ttu-id="b5089-123">Especifica o número de versão do evento.</span><span class="sxs-lookup"><span data-stu-id="b5089-123">Specifies the version number of the event.</span></span> <span data-ttu-id="b5089-124">Digite o número do evento.</span><span class="sxs-lookup"><span data-stu-id="b5089-124">Type the event number.</span></span> <span data-ttu-id="b5089-125">O PowerShell converte o número para o tipo de byte necessário.</span><span class="sxs-lookup"><span data-stu-id="b5089-125">PowerShell converts the number to the required Byte type.</span></span>

<span data-ttu-id="b5089-126">Este parâmetro permite que você especifique um evento quando versões diferentes do mesmo evento são definidas.</span><span class="sxs-lookup"><span data-stu-id="b5089-126">This parameter lets you specify an event when different versions of the same event are defined.</span></span>

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

### <span data-ttu-id="b5089-127">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b5089-127">CommonParameters</span></span>

<span data-ttu-id="b5089-128">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b5089-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b5089-129">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b5089-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b5089-130">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b5089-130">INPUTS</span></span>

### <span data-ttu-id="b5089-131">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b5089-131">None</span></span>

<span data-ttu-id="b5089-132">Este cmdlet não recebe entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="b5089-132">This cmdlet does not take input from the pipeline.</span></span>

## <span data-ttu-id="b5089-133">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b5089-133">OUTPUTS</span></span>

### <span data-ttu-id="b5089-134">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b5089-134">None</span></span>

<span data-ttu-id="b5089-135">Este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="b5089-135">This cmdlet does to generate any output.</span></span>

## <span data-ttu-id="b5089-136">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b5089-136">NOTES</span></span>

* <span data-ttu-id="b5089-137">Depois que o provedor grava o mesmo em um EventLog, você pode usar o cmdlet Get-WinEvent para obter o evento do log de eventos.</span><span class="sxs-lookup"><span data-stu-id="b5089-137">After the provider writes the even to an eventlog, you can use the Get-WinEvent cmdlet to get the event from the event log.</span></span>

## <span data-ttu-id="b5089-138">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b5089-138">RELATED LINKS</span></span>

[<span data-ttu-id="b5089-139">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="b5089-139">Get-WinEvent</span></span>](Get-WinEvent.md)

