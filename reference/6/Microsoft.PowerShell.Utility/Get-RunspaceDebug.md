---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-runspacedebug?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RunspaceDebug
ms.openlocfilehash: dbe78dd81641786b0079ef5326c849c2bde008dc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194476"
---
# <span data-ttu-id="ec86c-103">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="ec86c-103">Get-RunspaceDebug</span></span>

## <span data-ttu-id="ec86c-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="ec86c-104">SYNOPSIS</span></span>
<span data-ttu-id="ec86c-105">Mostra opções de depuração do runspace.</span><span class="sxs-lookup"><span data-stu-id="ec86c-105">Shows runspace debugging options.</span></span>

## <span data-ttu-id="ec86c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ec86c-106">SYNTAX</span></span>

### <span data-ttu-id="ec86c-107">RunspaceNameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="ec86c-107">RunspaceNameParameterSet (Default)</span></span>

```
Get-RunspaceDebug [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="ec86c-108">RunspaceParameterSet</span><span class="sxs-lookup"><span data-stu-id="ec86c-108">RunspaceParameterSet</span></span>

```
Get-RunspaceDebug [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="ec86c-109">RunspaceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="ec86c-109">RunspaceIdParameterSet</span></span>

```
Get-RunspaceDebug [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="ec86c-110">RunspaceInstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="ec86c-110">RunspaceInstanceIdParameterSet</span></span>

```
Get-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="ec86c-111">ProcessNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="ec86c-111">ProcessNameParameterSet</span></span>

```
Get-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="ec86c-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ec86c-112">DESCRIPTION</span></span>

<span data-ttu-id="ec86c-113">O `Get-RunspaceDebug` cmdlet mostra opções de depuração de runspace.</span><span class="sxs-lookup"><span data-stu-id="ec86c-113">The `Get-RunspaceDebug` cmdlet shows runspace debugging options.</span></span>

## <span data-ttu-id="ec86c-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="ec86c-114">EXAMPLES</span></span>

### <span data-ttu-id="ec86c-115">1: mostrar o estado do depurador de runspace padrão</span><span class="sxs-lookup"><span data-stu-id="ec86c-115">1: Show the state of the default runspace debugger</span></span>

```powershell
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            False      False
```

## <span data-ttu-id="ec86c-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ec86c-116">PARAMETERS</span></span>

### <span data-ttu-id="ec86c-117">-AppDomainname</span><span class="sxs-lookup"><span data-stu-id="ec86c-117">-AppDomainName</span></span>

<span data-ttu-id="ec86c-118">O nome do domínio do aplicativo que hospeda o runspace do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec86c-118">The name of the application domain that hosts the PowerShell runspace.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ec86c-119">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="ec86c-119">-ProcessName</span></span>

<span data-ttu-id="ec86c-120">O nome do processo que hospeda o runspace do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec86c-120">The name of the process that hosts the PowerShell runspace.</span></span>

```yaml
Type: System.String
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ec86c-121">-Runspace</span><span class="sxs-lookup"><span data-stu-id="ec86c-121">-Runspace</span></span>

<span data-ttu-id="ec86c-122">Um ou mais objetos de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="ec86c-122">One or more **Runspace** objects to be disabled.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.Runspace[]
Parameter Sets: RunspaceParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ec86c-123">-RunspaceId</span><span class="sxs-lookup"><span data-stu-id="ec86c-123">-RunspaceId</span></span>

<span data-ttu-id="ec86c-124">Um ou mais números de ID de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="ec86c-124">One or more **Runspace** Id numbers to be disabled.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: RunspaceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ec86c-125">-RunspaceInstanceId</span><span class="sxs-lookup"><span data-stu-id="ec86c-125">-RunspaceInstanceId</span></span>

<span data-ttu-id="ec86c-126">Um ou mais GUIDs de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="ec86c-126">One or more **Runspace** GUIDs to be disabled.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: RunspaceInstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ec86c-127">-RunspaceName</span><span class="sxs-lookup"><span data-stu-id="ec86c-127">-RunspaceName</span></span>

<span data-ttu-id="ec86c-128">Um ou mais nomes de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="ec86c-128">One or more **Runspace** names to be disabled.</span></span>

```yaml
Type: System.String[]
Parameter Sets: RunspaceNameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ec86c-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ec86c-129">CommonParameters</span></span>

<span data-ttu-id="ec86c-130">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ec86c-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ec86c-131">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ec86c-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ec86c-132">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="ec86c-132">INPUTS</span></span>

## <span data-ttu-id="ec86c-133">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="ec86c-133">OUTPUTS</span></span>

## <span data-ttu-id="ec86c-134">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="ec86c-134">NOTES</span></span>

## <span data-ttu-id="ec86c-135">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="ec86c-135">RELATED LINKS</span></span>

[<span data-ttu-id="ec86c-136">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="ec86c-136">Disable-RunspaceDebug</span></span>](Disable-RunspaceDebug.md)

[<span data-ttu-id="ec86c-137">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="ec86c-137">Enable-RunspaceDebug</span></span>](Enable-RunspaceDebug.md)
