---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-runspacedebug?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RunspaceDebug
ms.openlocfilehash: a77695fe32345fda8e6a0284cd29becb432a4273
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596191"
---
# <span data-ttu-id="0bbf0-102">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="0bbf0-102">Get-RunspaceDebug</span></span>

## <span data-ttu-id="0bbf0-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="0bbf0-103">SYNOPSIS</span></span>
<span data-ttu-id="0bbf0-104">Mostra opções de depuração do runspace.</span><span class="sxs-lookup"><span data-stu-id="0bbf0-104">Shows runspace debugging options.</span></span>

## <span data-ttu-id="0bbf0-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0bbf0-105">SYNTAX</span></span>

### <span data-ttu-id="0bbf0-106">RunspaceNameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="0bbf0-106">RunspaceNameParameterSet (Default)</span></span>

```
Get-RunspaceDebug [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="0bbf0-107">RunspaceParameterSet</span><span class="sxs-lookup"><span data-stu-id="0bbf0-107">RunspaceParameterSet</span></span>

```
Get-RunspaceDebug [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="0bbf0-108">RunspaceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="0bbf0-108">RunspaceIdParameterSet</span></span>

```
Get-RunspaceDebug [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="0bbf0-109">RunspaceInstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="0bbf0-109">RunspaceInstanceIdParameterSet</span></span>

```
Get-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="0bbf0-110">ProcessNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="0bbf0-110">ProcessNameParameterSet</span></span>

```
Get-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="0bbf0-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0bbf0-111">DESCRIPTION</span></span>

<span data-ttu-id="0bbf0-112">O `Get-RunspaceDebug` cmdlet mostra opções de depuração de runspace.</span><span class="sxs-lookup"><span data-stu-id="0bbf0-112">The `Get-RunspaceDebug` cmdlet shows runspace debugging options.</span></span>

## <span data-ttu-id="0bbf0-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="0bbf0-113">EXAMPLES</span></span>

### <span data-ttu-id="0bbf0-114">1: mostrar o estado do depurador de runspace padrão</span><span class="sxs-lookup"><span data-stu-id="0bbf0-114">1: Show the state of the default runspace debugger</span></span>

```powershell
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            False      False
```

## <span data-ttu-id="0bbf0-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0bbf0-115">PARAMETERS</span></span>

### <span data-ttu-id="0bbf0-116">-AppDomainname</span><span class="sxs-lookup"><span data-stu-id="0bbf0-116">-AppDomainName</span></span>

<span data-ttu-id="0bbf0-117">O nome do domínio do aplicativo que hospeda o runspace do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0bbf0-117">The name of the application domain that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="0bbf0-118">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="0bbf0-118">-ProcessName</span></span>

<span data-ttu-id="0bbf0-119">O nome do processo que hospeda o runspace do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0bbf0-119">The name of the process that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="0bbf0-120">-Runspace</span><span class="sxs-lookup"><span data-stu-id="0bbf0-120">-Runspace</span></span>

<span data-ttu-id="0bbf0-121">Um ou mais objetos de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="0bbf0-121">One or more **Runspace** objects to be disabled.</span></span>

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

### <span data-ttu-id="0bbf0-122">-RunspaceId</span><span class="sxs-lookup"><span data-stu-id="0bbf0-122">-RunspaceId</span></span>

<span data-ttu-id="0bbf0-123">Um ou mais números de ID de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="0bbf0-123">One or more **Runspace** Id numbers to be disabled.</span></span>

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

### <span data-ttu-id="0bbf0-124">-RunspaceInstanceId</span><span class="sxs-lookup"><span data-stu-id="0bbf0-124">-RunspaceInstanceId</span></span>

<span data-ttu-id="0bbf0-125">Um ou mais GUIDs de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="0bbf0-125">One or more **Runspace** GUIDs to be disabled.</span></span>

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

### <span data-ttu-id="0bbf0-126">-RunspaceName</span><span class="sxs-lookup"><span data-stu-id="0bbf0-126">-RunspaceName</span></span>

<span data-ttu-id="0bbf0-127">Um ou mais nomes de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="0bbf0-127">One or more **Runspace** names to be disabled.</span></span>

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

### <span data-ttu-id="0bbf0-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0bbf0-128">CommonParameters</span></span>

<span data-ttu-id="0bbf0-129">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0bbf0-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0bbf0-130">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0bbf0-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0bbf0-131">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="0bbf0-131">INPUTS</span></span>

## <span data-ttu-id="0bbf0-132">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="0bbf0-132">OUTPUTS</span></span>

## <span data-ttu-id="0bbf0-133">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="0bbf0-133">NOTES</span></span>

## <span data-ttu-id="0bbf0-134">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="0bbf0-134">RELATED LINKS</span></span>

[<span data-ttu-id="0bbf0-135">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="0bbf0-135">Disable-RunspaceDebug</span></span>](Disable-RunspaceDebug.md)

[<span data-ttu-id="0bbf0-136">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="0bbf0-136">Enable-RunspaceDebug</span></span>](Enable-RunspaceDebug.md)

