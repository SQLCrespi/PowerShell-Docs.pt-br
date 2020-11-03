---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/enable-runspacedebug?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-RunspaceDebug
ms.openlocfilehash: 54fb9500a924d2e5de98489fa4fb391accb23d0c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193834"
---
# <span data-ttu-id="2af99-103">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="2af99-103">Enable-RunspaceDebug</span></span>

## <span data-ttu-id="2af99-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="2af99-104">SYNOPSIS</span></span>
<span data-ttu-id="2af99-105">Habilita a depuração em Runspaces, em que qualquer ponto de interrupção é preservado até que um depurador seja anexado.</span><span class="sxs-lookup"><span data-stu-id="2af99-105">Enables debugging on runspaces where any breakpoint is preserved until a debugger is attached.</span></span>

## <span data-ttu-id="2af99-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2af99-106">SYNTAX</span></span>

### <span data-ttu-id="2af99-107">RunspaceNameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="2af99-107">RunspaceNameParameterSet (Default)</span></span>

```
Enable-RunspaceDebug [-BreakAll] [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="2af99-108">RunspaceParameterSet</span><span class="sxs-lookup"><span data-stu-id="2af99-108">RunspaceParameterSet</span></span>

```
Enable-RunspaceDebug [-BreakAll] [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="2af99-109">RunspaceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="2af99-109">RunspaceIdParameterSet</span></span>

```
Enable-RunspaceDebug [-BreakAll] [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="2af99-110">RunspaceInstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="2af99-110">RunspaceInstanceIdParameterSet</span></span>

```
Enable-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="2af99-111">ProcessNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="2af99-111">ProcessNameParameterSet</span></span>

```
Enable-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="2af99-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2af99-112">DESCRIPTION</span></span>

<span data-ttu-id="2af99-113">O `Enable-RunspaceDebug` cmdlet habilita a depuração em Runspaces, em que qualquer ponto de interrupção é preservado até que um depurador seja anexado.</span><span class="sxs-lookup"><span data-stu-id="2af99-113">The `Enable-RunspaceDebug` cmdlet enables debugging on runspaces where any breakpoint is preserved until a debugger is attached.</span></span>

## <span data-ttu-id="2af99-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="2af99-114">EXAMPLES</span></span>

### <span data-ttu-id="2af99-115">1: habilitar o depurador de runspace padrão</span><span class="sxs-lookup"><span data-stu-id="2af99-115">1: Enable the default runspace debugger</span></span>

```powershell
Enable-RunspaceDebug
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            True       False
```

## <span data-ttu-id="2af99-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2af99-116">PARAMETERS</span></span>

### <span data-ttu-id="2af99-117">-AppDomainname</span><span class="sxs-lookup"><span data-stu-id="2af99-117">-AppDomainName</span></span>

<span data-ttu-id="2af99-118">O nome do domínio do aplicativo que hospeda o runspace do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2af99-118">The name of the application domain that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="2af99-119">-BreakAll</span><span class="sxs-lookup"><span data-stu-id="2af99-119">-BreakAll</span></span>

<span data-ttu-id="2af99-120">Faz com que qualquer comando ou script em execução no runspace pare em modo de etapa, independentemente de um depurador estar anexado no momento.</span><span class="sxs-lookup"><span data-stu-id="2af99-120">Causes any running command or script in the Runspace to stop in step mode, regardless of whether a debugger is currently attached.</span></span> <span data-ttu-id="2af99-121">O script ou comando permanecerá parado até que um depurador seja anexado para depurar o ponto de interrupção atual.</span><span class="sxs-lookup"><span data-stu-id="2af99-121">The script or command will remain stopped until a debugger is attached to debug the current stop point.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RunspaceNameParameterSet, RunspaceParameterSet, RunspaceIdParameterSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2af99-122">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="2af99-122">-ProcessName</span></span>

<span data-ttu-id="2af99-123">O nome do processo que hospeda o runspace do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2af99-123">The name of the process that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="2af99-124">-Runspace</span><span class="sxs-lookup"><span data-stu-id="2af99-124">-Runspace</span></span>

<span data-ttu-id="2af99-125">Um ou mais objetos de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="2af99-125">One or more **Runspace** objects to be disabled.</span></span>

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

### <span data-ttu-id="2af99-126">-RunspaceId</span><span class="sxs-lookup"><span data-stu-id="2af99-126">-RunspaceId</span></span>

<span data-ttu-id="2af99-127">Um ou mais números de ID de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="2af99-127">One or more **Runspace** Id numbers to be disabled.</span></span>

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

### <span data-ttu-id="2af99-128">-RunspaceInstanceId</span><span class="sxs-lookup"><span data-stu-id="2af99-128">-RunspaceInstanceId</span></span>

<span data-ttu-id="2af99-129">Um ou mais GUIDs de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="2af99-129">One or more **Runspace** GUIDs to be disabled.</span></span>

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

### <span data-ttu-id="2af99-130">-RunspaceName</span><span class="sxs-lookup"><span data-stu-id="2af99-130">-RunspaceName</span></span>

<span data-ttu-id="2af99-131">Um ou mais nomes de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="2af99-131">One or more **Runspace** names to be disabled.</span></span>

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

### <span data-ttu-id="2af99-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2af99-132">CommonParameters</span></span>

<span data-ttu-id="2af99-133">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2af99-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2af99-134">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2af99-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2af99-135">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="2af99-135">INPUTS</span></span>

## <span data-ttu-id="2af99-136">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="2af99-136">OUTPUTS</span></span>

## <span data-ttu-id="2af99-137">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="2af99-137">NOTES</span></span>

## <span data-ttu-id="2af99-138">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="2af99-138">RELATED LINKS</span></span>

[<span data-ttu-id="2af99-139">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="2af99-139">Disable-RunspaceDebug</span></span>](Disable-RunspaceDebug.md)

[<span data-ttu-id="2af99-140">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="2af99-140">Get-RunspaceDebug</span></span>](Get-RunspaceDebug.md)
