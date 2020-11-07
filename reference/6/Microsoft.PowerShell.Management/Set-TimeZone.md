---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/18/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-timezone?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TimeZone
ms.openlocfilehash: 3738ac6202fa7a46c9a742e48edaeb1b82b5d749
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345112"
---
# <span data-ttu-id="a3a3b-103">Set-TimeZone</span><span class="sxs-lookup"><span data-stu-id="a3a3b-103">Set-TimeZone</span></span>

## <span data-ttu-id="a3a3b-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="a3a3b-104">SYNOPSIS</span></span>
<span data-ttu-id="a3a3b-105">Define o fuso horário do sistema para um fuso horário especificado.</span><span class="sxs-lookup"><span data-stu-id="a3a3b-105">Sets the system time zone to a specified time zone.</span></span>

## <span data-ttu-id="a3a3b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a3a3b-106">SYNTAX</span></span>

### <span data-ttu-id="a3a3b-107">Nome (padrão)</span><span class="sxs-lookup"><span data-stu-id="a3a3b-107">Name (Default)</span></span>

```
Set-TimeZone [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a3a3b-108">ID</span><span class="sxs-lookup"><span data-stu-id="a3a3b-108">Id</span></span>

```
Set-TimeZone -Id <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a3a3b-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="a3a3b-109">InputObject</span></span>

```
Set-TimeZone [-InputObject] <TimeZoneInfo> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a3a3b-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a3a3b-110">DESCRIPTION</span></span>

<span data-ttu-id="a3a3b-111">O `Set-TimeZone` cmdlet define o fuso horário do sistema para um fuso horário especificado.</span><span class="sxs-lookup"><span data-stu-id="a3a3b-111">The `Set-TimeZone` cmdlet sets the system time zone to a specified time zone.</span></span>

## <span data-ttu-id="a3a3b-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="a3a3b-112">EXAMPLES</span></span>

### <span data-ttu-id="a3a3b-113">Exemplo 1: definir o fuso horário por ID</span><span class="sxs-lookup"><span data-stu-id="a3a3b-113">Example 1: Set the time zone by Id</span></span>

<span data-ttu-id="a3a3b-114">Este exemplo define o fuso horário no computador local como horário padrão russo.</span><span class="sxs-lookup"><span data-stu-id="a3a3b-114">This example sets the time zone on the local computer to Russian Standard Time.</span></span>

```powershell
Set-TimeZone -Id "Russian Standard Time" -PassThru
```

```Output
Id                         : Russian Standard Time
DisplayName                : (UTC+03:00) Moscow, St. Petersburg
StandardName               : Russia TZ 2 Standard Time
DaylightName               : Russia TZ 2 Daylight Time
BaseUtcOffset              : 03:00:00
SupportsDaylightSavingTime : True
```

### <span data-ttu-id="a3a3b-115">Exemplo 2: definir o fuso horário por nome</span><span class="sxs-lookup"><span data-stu-id="a3a3b-115">Example 2: Set the time zone by name</span></span>

<span data-ttu-id="a3a3b-116">Este exemplo define o fuso horário no computador local como horário padrão russo.</span><span class="sxs-lookup"><span data-stu-id="a3a3b-116">This example sets the time zone on the local computer to Russian Standard Time.</span></span>

```powershell
Set-TimeZone -Name "Russia TZ 2 Standard Time"
```

<span data-ttu-id="a3a3b-117">Como vimos no exemplo anterior, a **ID** e o **nome** do fuso horário nem sempre correspondem.</span><span class="sxs-lookup"><span data-stu-id="a3a3b-117">As we saw in the previous example, the **Id** and the **Name** of the Time Zone do not always match.</span></span>
<span data-ttu-id="a3a3b-118">O parâmetro **Name** deve corresponder às propriedades **StandardName** ou **DaylightName** do objeto **TimeZoneInfo** .</span><span class="sxs-lookup"><span data-stu-id="a3a3b-118">The **Name** parameter must match the **StandardName** or **DaylightName** properties of the **TimeZoneInfo** object.</span></span>

## <span data-ttu-id="a3a3b-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a3a3b-119">PARAMETERS</span></span>

### <span data-ttu-id="a3a3b-120">-Id</span><span class="sxs-lookup"><span data-stu-id="a3a3b-120">-Id</span></span>

<span data-ttu-id="a3a3b-121">Especifica a ID do fuso horário definido por esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a3a3b-121">Specifies the ID of the time zone that this cmdlet sets.</span></span> <span data-ttu-id="a3a3b-122">Uma lista completa de IDs de fuso horário pode ser obtida executando o seguinte comando: `Get-TimeZone -ListAvailable` .</span><span class="sxs-lookup"><span data-stu-id="a3a3b-122">A full list of Time Zone IDs can be obtained by running the following command: `Get-TimeZone -ListAvailable`.</span></span>

```yaml
Type: System.String
Parameter Sets: Id
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a3a3b-123">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a3a3b-123">-InputObject</span></span>

<span data-ttu-id="a3a3b-124">Especifica um objeto **TimeZoneInfo** a ser usado como entrada.</span><span class="sxs-lookup"><span data-stu-id="a3a3b-124">Specifies a **TimeZoneInfo** object to use as input.</span></span>

```yaml
Type: System.TimeZoneInfo
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a3a3b-125">-Name</span><span class="sxs-lookup"><span data-stu-id="a3a3b-125">-Name</span></span>

<span data-ttu-id="a3a3b-126">Especifica o nome do fuso horário definido por esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a3a3b-126">Specifies the name of the time zone that this cmdlet sets.</span></span> <span data-ttu-id="a3a3b-127">É possível obter uma lista completa de nomes de fuso horário executando o seguinte comando: `Get-TimeZone -ListAvailable` .</span><span class="sxs-lookup"><span data-stu-id="a3a3b-127">A full list of Time Zone names can be obtained by running the following command: `Get-TimeZone -ListAvailable`.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a3a3b-128">-PassThru</span><span class="sxs-lookup"><span data-stu-id="a3a3b-128">-PassThru</span></span>

<span data-ttu-id="a3a3b-129">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="a3a3b-129">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="a3a3b-130">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="a3a3b-130">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="a3a3b-131">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a3a3b-131">-Confirm</span></span>

<span data-ttu-id="a3a3b-132">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a3a3b-132">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a3a3b-133">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a3a3b-133">-WhatIf</span></span>

<span data-ttu-id="a3a3b-134">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="a3a3b-134">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="a3a3b-135">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="a3a3b-135">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a3a3b-136">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a3a3b-136">CommonParameters</span></span>

<span data-ttu-id="a3a3b-137">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a3a3b-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a3a3b-138">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a3a3b-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a3a3b-139">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="a3a3b-139">INPUTS</span></span>

### <span data-ttu-id="a3a3b-140">System. String, System. TimeZoneInfo, System. String</span><span class="sxs-lookup"><span data-stu-id="a3a3b-140">System.String, System.TimeZoneInfo, System.String</span></span>

## <span data-ttu-id="a3a3b-141">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="a3a3b-141">OUTPUTS</span></span>

## <span data-ttu-id="a3a3b-142">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="a3a3b-142">NOTES</span></span>

<span data-ttu-id="a3a3b-143">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="a3a3b-143">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="a3a3b-144">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="a3a3b-144">RELATED LINKS</span></span>

[<span data-ttu-id="a3a3b-145">Get-TimeZone</span><span class="sxs-lookup"><span data-stu-id="a3a3b-145">Get-TimeZone</span></span>](Get-TimeZone.md)
