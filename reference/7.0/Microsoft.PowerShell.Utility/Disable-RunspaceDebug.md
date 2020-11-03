---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/disable-runspacedebug?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-RunspaceDebug
ms.openlocfilehash: 58665cd06e39784721be9a538b70dd8b7c2a1c14
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192952"
---
# <span data-ttu-id="f2cc8-103">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="f2cc8-103">Disable-RunspaceDebug</span></span>

## <span data-ttu-id="f2cc8-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="f2cc8-104">SYNOPSIS</span></span>
<span data-ttu-id="f2cc8-105">Desabilita a depuração em um ou mais Runspaces e libera qualquer interrupção de depurador pendente.</span><span class="sxs-lookup"><span data-stu-id="f2cc8-105">Disables debugging on one or more runspaces, and releases any pending debugger stop.</span></span>

## <span data-ttu-id="f2cc8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f2cc8-106">SYNTAX</span></span>

### <span data-ttu-id="f2cc8-107">RunspaceNameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="f2cc8-107">RunspaceNameParameterSet (Default)</span></span>

```
Disable-RunspaceDebug [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="f2cc8-108">RunspaceParameterSet</span><span class="sxs-lookup"><span data-stu-id="f2cc8-108">RunspaceParameterSet</span></span>

```
Disable-RunspaceDebug [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="f2cc8-109">RunspaceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="f2cc8-109">RunspaceIdParameterSet</span></span>

```
Disable-RunspaceDebug [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="f2cc8-110">RunspaceInstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="f2cc8-110">RunspaceInstanceIdParameterSet</span></span>

```
Disable-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="f2cc8-111">ProcessNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="f2cc8-111">ProcessNameParameterSet</span></span>

```
Disable-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="f2cc8-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f2cc8-112">DESCRIPTION</span></span>

<span data-ttu-id="f2cc8-113">O `Disable-RunspaceDebug` cmdlet desabilita a depuração em um ou mais Runspaces e libera qualquer interrupção de depurador pendente.</span><span class="sxs-lookup"><span data-stu-id="f2cc8-113">The `Disable-RunspaceDebug` cmdlet disables debugging on one or more runspaces, and releases any pending debugger stop.</span></span>

## <span data-ttu-id="f2cc8-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="f2cc8-114">EXAMPLES</span></span>

### <span data-ttu-id="f2cc8-115">1: desabilitar o depurador de runspace padrão</span><span class="sxs-lookup"><span data-stu-id="f2cc8-115">1: Disable the default runspace debugger</span></span>

```powershell
Disable-RunspaceDebug
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            False      False
```

## <span data-ttu-id="f2cc8-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f2cc8-116">PARAMETERS</span></span>

### <span data-ttu-id="f2cc8-117">-AppDomainname</span><span class="sxs-lookup"><span data-stu-id="f2cc8-117">-AppDomainName</span></span>

<span data-ttu-id="f2cc8-118">O nome do domínio do aplicativo que hospeda o runspace do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2cc8-118">The name of the application domain that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="f2cc8-119">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="f2cc8-119">-ProcessName</span></span>

<span data-ttu-id="f2cc8-120">O nome do processo que hospeda o runspace do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2cc8-120">The name of the process that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="f2cc8-121">-Runspace</span><span class="sxs-lookup"><span data-stu-id="f2cc8-121">-Runspace</span></span>

<span data-ttu-id="f2cc8-122">Um ou mais objetos de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="f2cc8-122">One or more **Runspace** objects to be disabled.</span></span>

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

### <span data-ttu-id="f2cc8-123">-RunspaceId</span><span class="sxs-lookup"><span data-stu-id="f2cc8-123">-RunspaceId</span></span>

<span data-ttu-id="f2cc8-124">Um ou mais números de ID de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="f2cc8-124">One or more **Runspace** Id numbers to be disabled.</span></span>

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

### <span data-ttu-id="f2cc8-125">-RunspaceInstanceId</span><span class="sxs-lookup"><span data-stu-id="f2cc8-125">-RunspaceInstanceId</span></span>

<span data-ttu-id="f2cc8-126">Um ou mais GUIDs de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="f2cc8-126">One or more **Runspace** GUIDs to be disabled.</span></span>

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

### <span data-ttu-id="f2cc8-127">-RunspaceName</span><span class="sxs-lookup"><span data-stu-id="f2cc8-127">-RunspaceName</span></span>

<span data-ttu-id="f2cc8-128">Um ou mais nomes de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="f2cc8-128">One or more **Runspace** names to be disabled.</span></span>

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

### <span data-ttu-id="f2cc8-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f2cc8-129">CommonParameters</span></span>

<span data-ttu-id="f2cc8-130">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f2cc8-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f2cc8-131">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f2cc8-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f2cc8-132">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="f2cc8-132">INPUTS</span></span>

## <span data-ttu-id="f2cc8-133">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="f2cc8-133">OUTPUTS</span></span>

## <span data-ttu-id="f2cc8-134">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="f2cc8-134">NOTES</span></span>

## <span data-ttu-id="f2cc8-135">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f2cc8-135">RELATED LINKS</span></span>

[<span data-ttu-id="f2cc8-136">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="f2cc8-136">Enable-RunspaceDebug</span></span>](Enable-RunspaceDebug.md)

[<span data-ttu-id="f2cc8-137">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="f2cc8-137">Get-RunspaceDebug</span></span>](Get-RunspaceDebug.md)
