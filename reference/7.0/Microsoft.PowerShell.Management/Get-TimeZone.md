---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-timezone?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TimeZone
ms.openlocfilehash: 44740fff5b8cef989d4c6391379741d1882f4734
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345605"
---
# <span data-ttu-id="32572-103">Get-TimeZone</span><span class="sxs-lookup"><span data-stu-id="32572-103">Get-TimeZone</span></span>

## <span data-ttu-id="32572-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="32572-104">SYNOPSIS</span></span>
<span data-ttu-id="32572-105">Obtém o fuso horário atual ou uma lista de fusos horários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="32572-105">Gets the current time zone or a list of available time zones.</span></span>

## <span data-ttu-id="32572-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="32572-106">SYNTAX</span></span>

### <span data-ttu-id="32572-107">Nome (padrão)</span><span class="sxs-lookup"><span data-stu-id="32572-107">Name (Default)</span></span>

```
Get-TimeZone [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="32572-108">ID</span><span class="sxs-lookup"><span data-stu-id="32572-108">Id</span></span>

```
Get-TimeZone -Id <String[]> [<CommonParameters>]
```

### <span data-ttu-id="32572-109">ListAvailable</span><span class="sxs-lookup"><span data-stu-id="32572-109">ListAvailable</span></span>

```
Get-TimeZone [-ListAvailable] [<CommonParameters>]
```

## <span data-ttu-id="32572-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="32572-110">DESCRIPTION</span></span>

<span data-ttu-id="32572-111">O cmdlet **Get-TimeZone** Obtém o fuso horário atual ou uma lista de fusos horários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="32572-111">The **Get-TimeZone** cmdlet gets the current time zone or a list of available time zones.</span></span>

## <span data-ttu-id="32572-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="32572-112">EXAMPLES</span></span>

### <span data-ttu-id="32572-113">Exemplo 1: obter o fuso horário atual</span><span class="sxs-lookup"><span data-stu-id="32572-113">Example 1: Get the current time zone</span></span>

```
PS C:\> Get-TimeZone
Pacific Standard Time
```

<span data-ttu-id="32572-114">Esse comando obtém o fuso horário atual.</span><span class="sxs-lookup"><span data-stu-id="32572-114">This command gets the current time zone.</span></span>

### <span data-ttu-id="32572-115">Exemplo 2: obter fusos horários que correspondem a uma cadeia de caracteres especificada</span><span class="sxs-lookup"><span data-stu-id="32572-115">Example 2: Get time zones that match a specified string</span></span>

```
PS C:\> Get-TimeZone -Name "*pac*"
Pacific Standard Time (Mexico)

(UTC-08:00) Pacific Time (US &amp; Canada)

Pacific Standard Time

SA Pacific Standard Time

Pacific SA Standard Time

West Pacific Standard Time

Central Pacific Standard Time
```

<span data-ttu-id="32572-116">Esse comando obtém todos os fusos horários que correspondem ao curinga especificado.</span><span class="sxs-lookup"><span data-stu-id="32572-116">This command gets all time zones that match the specified wildcard.</span></span>

### <span data-ttu-id="32572-117">Exemplo 3: obter todos os fusos horários disponíveis</span><span class="sxs-lookup"><span data-stu-id="32572-117">Example 3: Get all available time zones</span></span>

```
PS C:\> Get-TimeZone -ListAvailable
```

<span data-ttu-id="32572-118">Esse comando obtém todos os fusos horários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="32572-118">This command gets all available time zones.</span></span>

## <span data-ttu-id="32572-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="32572-119">PARAMETERS</span></span>

### <span data-ttu-id="32572-120">-Id</span><span class="sxs-lookup"><span data-stu-id="32572-120">-Id</span></span>

<span data-ttu-id="32572-121">Especifica, como uma matriz de cadeia de caracteres, a ID ou IDs dos fusos horários que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="32572-121">Specifies, as a string array, the ID or IDs of the time zones that this cmdlet gets.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Id
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="32572-122">-ListAvailable</span><span class="sxs-lookup"><span data-stu-id="32572-122">-ListAvailable</span></span>

<span data-ttu-id="32572-123">Indica que este cmdlet obtém todos os fusos horários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="32572-123">Indicates that this cmdlet gets all available time zones.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ListAvailable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="32572-124">-Name</span><span class="sxs-lookup"><span data-stu-id="32572-124">-Name</span></span>

<span data-ttu-id="32572-125">Especifica, como uma matriz de cadeia de caracteres, o nome ou os nomes dos fusos horários que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="32572-125">Specifies, as a string array, the name or names of the time zones that this cmdlet gets.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="32572-126">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="32572-126">CommonParameters</span></span>

<span data-ttu-id="32572-127">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="32572-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="32572-128">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="32572-128">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="32572-129">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="32572-129">INPUTS</span></span>

### <span data-ttu-id="32572-130">System.String[]</span><span class="sxs-lookup"><span data-stu-id="32572-130">System.String[]</span></span>

## <span data-ttu-id="32572-131">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="32572-131">OUTPUTS</span></span>

### <span data-ttu-id="32572-132">System. TimeZoneInfo []</span><span class="sxs-lookup"><span data-stu-id="32572-132">System.TimeZoneInfo[]</span></span>

## <span data-ttu-id="32572-133">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="32572-133">NOTES</span></span>

<span data-ttu-id="32572-134">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="32572-134">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="32572-135">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="32572-135">RELATED LINKS</span></span>

[<span data-ttu-id="32572-136">Set-TimeZone</span><span class="sxs-lookup"><span data-stu-id="32572-136">Set-TimeZone</span></span>](Set-TimeZone.md)
