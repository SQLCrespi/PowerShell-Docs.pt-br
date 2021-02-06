---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/enable-runspacedebug?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-RunspaceDebug
ms.openlocfilehash: 26ab9b9135eedafa0238eab5c07aa7abb7880ed4
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596798"
---
# <span data-ttu-id="e6887-102">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="e6887-102">Enable-RunspaceDebug</span></span>

## <span data-ttu-id="e6887-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="e6887-103">SYNOPSIS</span></span>
<span data-ttu-id="e6887-104">Habilita a depuração em Runspaces, em que qualquer ponto de interrupção é preservado até que um depurador seja anexado.</span><span class="sxs-lookup"><span data-stu-id="e6887-104">Enables debugging on runspaces where any breakpoint is preserved until a debugger is attached.</span></span>

## <span data-ttu-id="e6887-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e6887-105">SYNTAX</span></span>

### <span data-ttu-id="e6887-106">RunspaceNameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="e6887-106">RunspaceNameParameterSet (Default)</span></span>

```
Enable-RunspaceDebug [-BreakAll] [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="e6887-107">RunspaceParameterSet</span><span class="sxs-lookup"><span data-stu-id="e6887-107">RunspaceParameterSet</span></span>

```
Enable-RunspaceDebug [-BreakAll] [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="e6887-108">RunspaceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="e6887-108">RunspaceIdParameterSet</span></span>

```
Enable-RunspaceDebug [-BreakAll] [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="e6887-109">RunspaceInstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="e6887-109">RunspaceInstanceIdParameterSet</span></span>

```
Enable-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="e6887-110">ProcessNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="e6887-110">ProcessNameParameterSet</span></span>

```
Enable-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="e6887-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e6887-111">DESCRIPTION</span></span>

<span data-ttu-id="e6887-112">O `Enable-RunspaceDebug` cmdlet habilita a depuração em Runspaces, em que qualquer ponto de interrupção é preservado até que um depurador seja anexado.</span><span class="sxs-lookup"><span data-stu-id="e6887-112">The `Enable-RunspaceDebug` cmdlet enables debugging on runspaces where any breakpoint is preserved until a debugger is attached.</span></span>

## <span data-ttu-id="e6887-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e6887-113">EXAMPLES</span></span>

### <span data-ttu-id="e6887-114">1: habilitar o depurador de runspace padrão</span><span class="sxs-lookup"><span data-stu-id="e6887-114">1: Enable the default runspace debugger</span></span>

```powershell
Enable-RunspaceDebug
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            True       False
```

## <span data-ttu-id="e6887-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e6887-115">PARAMETERS</span></span>

### <span data-ttu-id="e6887-116">-AppDomainname</span><span class="sxs-lookup"><span data-stu-id="e6887-116">-AppDomainName</span></span>

<span data-ttu-id="e6887-117">O nome do domínio do aplicativo que hospeda o runspace do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6887-117">The name of the application domain that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="e6887-118">-BreakAll</span><span class="sxs-lookup"><span data-stu-id="e6887-118">-BreakAll</span></span>

<span data-ttu-id="e6887-119">Faz com que qualquer comando ou script em execução no runspace pare em modo de etapa, independentemente de um depurador estar anexado no momento.</span><span class="sxs-lookup"><span data-stu-id="e6887-119">Causes any running command or script in the Runspace to stop in step mode, regardless of whether a debugger is currently attached.</span></span> <span data-ttu-id="e6887-120">O script ou comando permanecerá parado até que um depurador seja anexado para depurar o ponto de interrupção atual.</span><span class="sxs-lookup"><span data-stu-id="e6887-120">The script or command will remain stopped until a debugger is attached to debug the current stop point.</span></span>

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

### <span data-ttu-id="e6887-121">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="e6887-121">-ProcessName</span></span>

<span data-ttu-id="e6887-122">O nome do processo que hospeda o runspace do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6887-122">The name of the process that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="e6887-123">-Runspace</span><span class="sxs-lookup"><span data-stu-id="e6887-123">-Runspace</span></span>

<span data-ttu-id="e6887-124">Um ou mais objetos de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="e6887-124">One or more **Runspace** objects to be disabled.</span></span>

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

### <span data-ttu-id="e6887-125">-RunspaceId</span><span class="sxs-lookup"><span data-stu-id="e6887-125">-RunspaceId</span></span>

<span data-ttu-id="e6887-126">Um ou mais números de ID de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="e6887-126">One or more **Runspace** Id numbers to be disabled.</span></span>

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

### <span data-ttu-id="e6887-127">-RunspaceInstanceId</span><span class="sxs-lookup"><span data-stu-id="e6887-127">-RunspaceInstanceId</span></span>

<span data-ttu-id="e6887-128">Um ou mais GUIDs de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="e6887-128">One or more **Runspace** GUIDs to be disabled.</span></span>

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

### <span data-ttu-id="e6887-129">-RunspaceName</span><span class="sxs-lookup"><span data-stu-id="e6887-129">-RunspaceName</span></span>

<span data-ttu-id="e6887-130">Um ou mais nomes de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="e6887-130">One or more **Runspace** names to be disabled.</span></span>

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

### <span data-ttu-id="e6887-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e6887-131">CommonParameters</span></span>

<span data-ttu-id="e6887-132">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e6887-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e6887-133">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e6887-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e6887-134">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="e6887-134">INPUTS</span></span>

## <span data-ttu-id="e6887-135">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="e6887-135">OUTPUTS</span></span>

## <span data-ttu-id="e6887-136">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e6887-136">NOTES</span></span>

## <span data-ttu-id="e6887-137">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e6887-137">RELATED LINKS</span></span>

[<span data-ttu-id="e6887-138">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="e6887-138">Disable-RunspaceDebug</span></span>](Disable-RunspaceDebug.md)

[<span data-ttu-id="e6887-139">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="e6887-139">Get-RunspaceDebug</span></span>](Get-RunspaceDebug.md)

