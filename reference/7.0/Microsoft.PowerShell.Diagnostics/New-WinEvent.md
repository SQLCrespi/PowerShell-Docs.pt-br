---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/new-winevent?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WinEvent
ms.openlocfilehash: 8e64c3e3a782fadf1669f1310d1615f3a014ccee
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192817"
---
# <span data-ttu-id="a798d-103">New-WinEvent</span><span class="sxs-lookup"><span data-stu-id="a798d-103">New-WinEvent</span></span>

## <span data-ttu-id="a798d-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="a798d-104">SYNOPSIS</span></span>
<span data-ttu-id="a798d-105">Cria um novo evento do Windows para o provedor de eventos especificado.</span><span class="sxs-lookup"><span data-stu-id="a798d-105">Creates a new Windows event for the specified event provider.</span></span>

## <span data-ttu-id="a798d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a798d-106">SYNTAX</span></span>

```
New-WinEvent [-ProviderName] <String> [-Id] <Int32> [-Version <Byte>] [[-Payload] <Object[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="a798d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a798d-107">DESCRIPTION</span></span>

<span data-ttu-id="a798d-108">O **New-WinEvent** cria um evento de rastreamento de eventos do Windows (ETW) para um provedor de eventos.</span><span class="sxs-lookup"><span data-stu-id="a798d-108">The **New-WinEvent** cmdlet creates an Event Tracing for Windows (ETW) event for an event provider.</span></span>
<span data-ttu-id="a798d-109">Você pode usar este cmdlet para adicionar eventos a canais ETW do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a798d-109">You can use this cmdlet to add events to ETW channels from PowerShell.</span></span>

## <span data-ttu-id="a798d-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="a798d-110">EXAMPLES</span></span>

### <span data-ttu-id="a798d-111">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="a798d-111">Example 1</span></span>

```powershell
PS C:\> New-WinEvent -ProviderName Microsoft-Windows-PowerShell -Id 45090 -Payload @("Workflow", "Running")
```

<span data-ttu-id="a798d-112">Este comando usa o cmdlet **New-WinEvent** para criar o evento 45090 para o provedor Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a798d-112">This command uses the **New-WinEvent** cmdlet to create event 45090 for the Microsoft-Windows-PowerShell provider.</span></span>

## <span data-ttu-id="a798d-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a798d-113">PARAMETERS</span></span>

### <span data-ttu-id="a798d-114">-Id</span><span class="sxs-lookup"><span data-stu-id="a798d-114">-Id</span></span>

<span data-ttu-id="a798d-115">Especifica um identificador de evento que foi registrado por meio de um manifesto de instrumentação.</span><span class="sxs-lookup"><span data-stu-id="a798d-115">Specifies an event id that was registered through an instrumentation manifest.</span></span>

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

### <span data-ttu-id="a798d-116">-Conteúdo</span><span class="sxs-lookup"><span data-stu-id="a798d-116">-Payload</span></span>

<span data-ttu-id="a798d-117">Especifica a mensagem para o evento.</span><span class="sxs-lookup"><span data-stu-id="a798d-117">Specifies the message for the event.</span></span> <span data-ttu-id="a798d-118">Quando os eventos são gravados em um log de eventos, a carga é armazenada na propriedade **Message** do objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="a798d-118">When the event is written to an event log, the payload is stored in the **Message** property of the event object.</span></span>

<span data-ttu-id="a798d-119">Quando a carga especificada não corresponder à carga na definição de evento, o PowerShell gerará um aviso, mas o comando ainda terá sucesso.</span><span class="sxs-lookup"><span data-stu-id="a798d-119">When the specified payload does not match the payload in the event definition, PowerShell generates a warning, but the command still succeeds.</span></span>

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

### <span data-ttu-id="a798d-120">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="a798d-120">-ProviderName</span></span>

<span data-ttu-id="a798d-121">Especifica o provedor de eventos que grava o evento em um log de eventos, como "Microsoft-Windows-PowerShell".</span><span class="sxs-lookup"><span data-stu-id="a798d-121">Specifies the event provider that writes the event to an event log, such as "Microsoft-Windows-PowerShell".</span></span> <span data-ttu-id="a798d-122">Um provedor de eventos ETW é uma entidade lógica que grava eventos em sessões de ETW.</span><span class="sxs-lookup"><span data-stu-id="a798d-122">An ETW event provider is a logical entity that writes events to ETW sessions.</span></span>

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

### <span data-ttu-id="a798d-123">-Version</span><span class="sxs-lookup"><span data-stu-id="a798d-123">-Version</span></span>

<span data-ttu-id="a798d-124">Especifica o número de versão do evento.</span><span class="sxs-lookup"><span data-stu-id="a798d-124">Specifies the version number of the event.</span></span> <span data-ttu-id="a798d-125">Digite o número do evento.</span><span class="sxs-lookup"><span data-stu-id="a798d-125">Type the event number.</span></span> <span data-ttu-id="a798d-126">O PowerShell converte o número para o tipo de byte necessário.</span><span class="sxs-lookup"><span data-stu-id="a798d-126">PowerShell converts the number to the required Byte type.</span></span>

<span data-ttu-id="a798d-127">Este parâmetro permite que você especifique um evento quando versões diferentes do mesmo evento são definidas.</span><span class="sxs-lookup"><span data-stu-id="a798d-127">This parameter lets you specify an event when different versions of the same event are defined.</span></span>

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

### <span data-ttu-id="a798d-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a798d-128">CommonParameters</span></span>

<span data-ttu-id="a798d-129">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a798d-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a798d-130">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a798d-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a798d-131">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="a798d-131">INPUTS</span></span>

### <span data-ttu-id="a798d-132">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a798d-132">None</span></span>

<span data-ttu-id="a798d-133">Este cmdlet não recebe entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="a798d-133">This cmdlet does not take input from the pipeline.</span></span>

## <span data-ttu-id="a798d-134">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="a798d-134">OUTPUTS</span></span>

### <span data-ttu-id="a798d-135">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a798d-135">None</span></span>

<span data-ttu-id="a798d-136">Este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="a798d-136">This cmdlet does to generate any output.</span></span>

## <span data-ttu-id="a798d-137">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="a798d-137">NOTES</span></span>

* <span data-ttu-id="a798d-138">Depois que o provedor grava o mesmo em um EventLog, você pode usar o cmdlet Get-WinEvent para obter o evento do log de eventos.</span><span class="sxs-lookup"><span data-stu-id="a798d-138">After the provider writes the even to an eventlog, you can use the Get-WinEvent cmdlet to get the event from the event log.</span></span>

## <span data-ttu-id="a798d-139">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="a798d-139">RELATED LINKS</span></span>

[<span data-ttu-id="a798d-140">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="a798d-140">Get-WinEvent</span></span>](Get-WinEvent.md)
