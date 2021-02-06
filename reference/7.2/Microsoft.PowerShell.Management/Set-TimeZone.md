---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/18/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-timezone?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TimeZone
ms.openlocfilehash: ddce638972aabb1afc1c8fe500df380dd01dff14
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597832"
---
# <span data-ttu-id="d33f9-102">Set-TimeZone</span><span class="sxs-lookup"><span data-stu-id="d33f9-102">Set-TimeZone</span></span>

## <span data-ttu-id="d33f9-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d33f9-103">SYNOPSIS</span></span>
<span data-ttu-id="d33f9-104">Define o fuso horário do sistema para um fuso horário especificado.</span><span class="sxs-lookup"><span data-stu-id="d33f9-104">Sets the system time zone to a specified time zone.</span></span>

## <span data-ttu-id="d33f9-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d33f9-105">SYNTAX</span></span>

### <span data-ttu-id="d33f9-106">Nome (padrão)</span><span class="sxs-lookup"><span data-stu-id="d33f9-106">Name (Default)</span></span>

```
Set-TimeZone [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d33f9-107">ID</span><span class="sxs-lookup"><span data-stu-id="d33f9-107">Id</span></span>

```
Set-TimeZone -Id <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d33f9-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="d33f9-108">InputObject</span></span>

```
Set-TimeZone [-InputObject] <TimeZoneInfo> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d33f9-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d33f9-109">DESCRIPTION</span></span>

<span data-ttu-id="d33f9-110">O `Set-TimeZone` cmdlet define o fuso horário do sistema para um fuso horário especificado.</span><span class="sxs-lookup"><span data-stu-id="d33f9-110">The `Set-TimeZone` cmdlet sets the system time zone to a specified time zone.</span></span>

## <span data-ttu-id="d33f9-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d33f9-111">EXAMPLES</span></span>

### <span data-ttu-id="d33f9-112">Exemplo 1: definir o fuso horário por ID</span><span class="sxs-lookup"><span data-stu-id="d33f9-112">Example 1: Set the time zone by Id</span></span>

<span data-ttu-id="d33f9-113">Este exemplo define o fuso horário no computador local como horário padrão russo.</span><span class="sxs-lookup"><span data-stu-id="d33f9-113">This example sets the time zone on the local computer to Russian Standard Time.</span></span>

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

### <span data-ttu-id="d33f9-114">Exemplo 2: definir o fuso horário por nome</span><span class="sxs-lookup"><span data-stu-id="d33f9-114">Example 2: Set the time zone by name</span></span>

<span data-ttu-id="d33f9-115">Este exemplo define o fuso horário no computador local como horário padrão russo.</span><span class="sxs-lookup"><span data-stu-id="d33f9-115">This example sets the time zone on the local computer to Russian Standard Time.</span></span>

```powershell
Set-TimeZone -Name "Russia TZ 2 Standard Time"
```

<span data-ttu-id="d33f9-116">Como vimos no exemplo anterior, a **ID** e o **nome** do fuso horário nem sempre correspondem.</span><span class="sxs-lookup"><span data-stu-id="d33f9-116">As we saw in the previous example, the **Id** and the **Name** of the Time Zone do not always match.</span></span>
<span data-ttu-id="d33f9-117">O parâmetro **Name** deve corresponder às propriedades **StandardName** ou **DaylightName** do objeto **TimeZoneInfo** .</span><span class="sxs-lookup"><span data-stu-id="d33f9-117">The **Name** parameter must match the **StandardName** or **DaylightName** properties of the **TimeZoneInfo** object.</span></span>

## <span data-ttu-id="d33f9-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d33f9-118">PARAMETERS</span></span>

### <span data-ttu-id="d33f9-119">-Id</span><span class="sxs-lookup"><span data-stu-id="d33f9-119">-Id</span></span>

<span data-ttu-id="d33f9-120">Especifica a ID do fuso horário definido por esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d33f9-120">Specifies the ID of the time zone that this cmdlet sets.</span></span> <span data-ttu-id="d33f9-121">Uma lista completa de IDs de fuso horário pode ser obtida executando o seguinte comando: `Get-TimeZone -ListAvailable` .</span><span class="sxs-lookup"><span data-stu-id="d33f9-121">A full list of Time Zone IDs can be obtained by running the following command: `Get-TimeZone -ListAvailable`.</span></span>

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

### <span data-ttu-id="d33f9-122">-InputObject</span><span class="sxs-lookup"><span data-stu-id="d33f9-122">-InputObject</span></span>

<span data-ttu-id="d33f9-123">Especifica um objeto **TimeZoneInfo** a ser usado como entrada.</span><span class="sxs-lookup"><span data-stu-id="d33f9-123">Specifies a **TimeZoneInfo** object to use as input.</span></span>

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

### <span data-ttu-id="d33f9-124">-Name</span><span class="sxs-lookup"><span data-stu-id="d33f9-124">-Name</span></span>

<span data-ttu-id="d33f9-125">Especifica o nome do fuso horário definido por esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d33f9-125">Specifies the name of the time zone that this cmdlet sets.</span></span> <span data-ttu-id="d33f9-126">É possível obter uma lista completa de nomes de fuso horário executando o seguinte comando: `Get-TimeZone -ListAvailable` .</span><span class="sxs-lookup"><span data-stu-id="d33f9-126">A full list of Time Zone names can be obtained by running the following command: `Get-TimeZone -ListAvailable`.</span></span>

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

### <span data-ttu-id="d33f9-127">-PassThru</span><span class="sxs-lookup"><span data-stu-id="d33f9-127">-PassThru</span></span>

<span data-ttu-id="d33f9-128">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="d33f9-128">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="d33f9-129">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="d33f9-129">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="d33f9-130">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d33f9-130">-Confirm</span></span>

<span data-ttu-id="d33f9-131">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d33f9-131">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d33f9-132">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d33f9-132">-WhatIf</span></span>

<span data-ttu-id="d33f9-133">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="d33f9-133">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="d33f9-134">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="d33f9-134">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d33f9-135">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d33f9-135">CommonParameters</span></span>

<span data-ttu-id="d33f9-136">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d33f9-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d33f9-137">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d33f9-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d33f9-138">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d33f9-138">INPUTS</span></span>

### <span data-ttu-id="d33f9-139">System. String, System. TimeZoneInfo, System. String</span><span class="sxs-lookup"><span data-stu-id="d33f9-139">System.String, System.TimeZoneInfo, System.String</span></span>

## <span data-ttu-id="d33f9-140">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d33f9-140">OUTPUTS</span></span>

## <span data-ttu-id="d33f9-141">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d33f9-141">NOTES</span></span>

<span data-ttu-id="d33f9-142">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="d33f9-142">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="d33f9-143">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d33f9-143">RELATED LINKS</span></span>

[<span data-ttu-id="d33f9-144">Get-TimeZone</span><span class="sxs-lookup"><span data-stu-id="d33f9-144">Get-TimeZone</span></span>](Get-TimeZone.md)
