---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/disable-runspacedebug?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-RunspaceDebug
ms.openlocfilehash: 7a014c456a28f3fde8b272ee45e0d0c264131718
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194277"
---
# <span data-ttu-id="ada38-103">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="ada38-103">Disable-RunspaceDebug</span></span>

## <span data-ttu-id="ada38-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="ada38-104">SYNOPSIS</span></span>
<span data-ttu-id="ada38-105">Desabilita a depuração em um ou mais Runspaces e libera qualquer interrupção de depurador pendente.</span><span class="sxs-lookup"><span data-stu-id="ada38-105">Disables debugging on one or more runspaces, and releases any pending debugger stop.</span></span>

## <span data-ttu-id="ada38-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ada38-106">SYNTAX</span></span>

### <span data-ttu-id="ada38-107">RunspaceNameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="ada38-107">RunspaceNameParameterSet (Default)</span></span>

```
Disable-RunspaceDebug [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="ada38-108">RunspaceParameterSet</span><span class="sxs-lookup"><span data-stu-id="ada38-108">RunspaceParameterSet</span></span>

```
Disable-RunspaceDebug [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="ada38-109">RunspaceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="ada38-109">RunspaceIdParameterSet</span></span>

```
Disable-RunspaceDebug [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="ada38-110">RunspaceInstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="ada38-110">RunspaceInstanceIdParameterSet</span></span>

```
Disable-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="ada38-111">ProcessNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="ada38-111">ProcessNameParameterSet</span></span>

```
Disable-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="ada38-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ada38-112">DESCRIPTION</span></span>

<span data-ttu-id="ada38-113">O `Disable-RunspaceDebug` cmdlet desabilita a depuração em um ou mais Runspaces e libera qualquer interrupção de depurador pendente.</span><span class="sxs-lookup"><span data-stu-id="ada38-113">The `Disable-RunspaceDebug` cmdlet disables debugging on one or more runspaces, and releases any pending debugger stop.</span></span>

## <span data-ttu-id="ada38-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="ada38-114">EXAMPLES</span></span>

### <span data-ttu-id="ada38-115">1: desabilitar o depurador de runspace padrão</span><span class="sxs-lookup"><span data-stu-id="ada38-115">1: Disable the default runspace debugger</span></span>

```powershell
Disable-RunspaceDebug
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            False      False
```

## <span data-ttu-id="ada38-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ada38-116">PARAMETERS</span></span>

### <span data-ttu-id="ada38-117">-AppDomainname</span><span class="sxs-lookup"><span data-stu-id="ada38-117">-AppDomainName</span></span>

<span data-ttu-id="ada38-118">O nome do domínio do aplicativo que hospeda o runspace do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ada38-118">The name of the application domain that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="ada38-119">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="ada38-119">-ProcessName</span></span>

<span data-ttu-id="ada38-120">O nome do processo que hospeda o runspace do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ada38-120">The name of the process that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="ada38-121">-Runspace</span><span class="sxs-lookup"><span data-stu-id="ada38-121">-Runspace</span></span>

<span data-ttu-id="ada38-122">Um ou mais objetos de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="ada38-122">One or more **Runspace** objects to be disabled.</span></span>

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

### <span data-ttu-id="ada38-123">-RunspaceId</span><span class="sxs-lookup"><span data-stu-id="ada38-123">-RunspaceId</span></span>

<span data-ttu-id="ada38-124">Um ou mais números de ID de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="ada38-124">One or more **Runspace** Id numbers to be disabled.</span></span>

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

### <span data-ttu-id="ada38-125">-RunspaceInstanceId</span><span class="sxs-lookup"><span data-stu-id="ada38-125">-RunspaceInstanceId</span></span>

<span data-ttu-id="ada38-126">Um ou mais GUIDs de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="ada38-126">One or more **Runspace** GUIDs to be disabled.</span></span>

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

### <span data-ttu-id="ada38-127">-RunspaceName</span><span class="sxs-lookup"><span data-stu-id="ada38-127">-RunspaceName</span></span>

<span data-ttu-id="ada38-128">Um ou mais nomes de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="ada38-128">One or more **Runspace** names to be disabled.</span></span>

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

### <span data-ttu-id="ada38-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ada38-129">CommonParameters</span></span>

<span data-ttu-id="ada38-130">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ada38-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ada38-131">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ada38-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ada38-132">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="ada38-132">INPUTS</span></span>

## <span data-ttu-id="ada38-133">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="ada38-133">OUTPUTS</span></span>

## <span data-ttu-id="ada38-134">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="ada38-134">NOTES</span></span>

## <span data-ttu-id="ada38-135">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="ada38-135">RELATED LINKS</span></span>

[<span data-ttu-id="ada38-136">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="ada38-136">Enable-RunspaceDebug</span></span>](Enable-RunspaceDebug.md)

[<span data-ttu-id="ada38-137">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="ada38-137">Get-RunspaceDebug</span></span>](Get-RunspaceDebug.md)

