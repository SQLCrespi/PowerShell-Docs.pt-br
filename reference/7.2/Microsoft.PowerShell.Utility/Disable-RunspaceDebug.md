---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/disable-runspacedebug?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-RunspaceDebug
ms.openlocfilehash: 589c8cb36a91de510ffc30973fe70729700ad020
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596383"
---
# <span data-ttu-id="6071b-102">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="6071b-102">Disable-RunspaceDebug</span></span>

## <span data-ttu-id="6071b-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="6071b-103">SYNOPSIS</span></span>
<span data-ttu-id="6071b-104">Desabilita a depuração em um ou mais Runspaces e libera qualquer interrupção de depurador pendente.</span><span class="sxs-lookup"><span data-stu-id="6071b-104">Disables debugging on one or more runspaces, and releases any pending debugger stop.</span></span>

## <span data-ttu-id="6071b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6071b-105">SYNTAX</span></span>

### <span data-ttu-id="6071b-106">RunspaceNameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="6071b-106">RunspaceNameParameterSet (Default)</span></span>

```
Disable-RunspaceDebug [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="6071b-107">RunspaceParameterSet</span><span class="sxs-lookup"><span data-stu-id="6071b-107">RunspaceParameterSet</span></span>

```
Disable-RunspaceDebug [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="6071b-108">RunspaceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="6071b-108">RunspaceIdParameterSet</span></span>

```
Disable-RunspaceDebug [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="6071b-109">RunspaceInstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="6071b-109">RunspaceInstanceIdParameterSet</span></span>

```
Disable-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="6071b-110">ProcessNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="6071b-110">ProcessNameParameterSet</span></span>

```
Disable-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="6071b-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6071b-111">DESCRIPTION</span></span>

<span data-ttu-id="6071b-112">O `Disable-RunspaceDebug` cmdlet desabilita a depuração em um ou mais Runspaces e libera qualquer interrupção de depurador pendente.</span><span class="sxs-lookup"><span data-stu-id="6071b-112">The `Disable-RunspaceDebug` cmdlet disables debugging on one or more runspaces, and releases any pending debugger stop.</span></span>

## <span data-ttu-id="6071b-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="6071b-113">EXAMPLES</span></span>

### <span data-ttu-id="6071b-114">1: desabilitar o depurador de runspace padrão</span><span class="sxs-lookup"><span data-stu-id="6071b-114">1: Disable the default runspace debugger</span></span>

```powershell
Disable-RunspaceDebug
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            False      False
```

## <span data-ttu-id="6071b-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6071b-115">PARAMETERS</span></span>

### <span data-ttu-id="6071b-116">-AppDomainname</span><span class="sxs-lookup"><span data-stu-id="6071b-116">-AppDomainName</span></span>

<span data-ttu-id="6071b-117">O nome do domínio do aplicativo que hospeda o runspace do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6071b-117">The name of the application domain that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="6071b-118">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="6071b-118">-ProcessName</span></span>

<span data-ttu-id="6071b-119">O nome do processo que hospeda o runspace do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6071b-119">The name of the process that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="6071b-120">-Runspace</span><span class="sxs-lookup"><span data-stu-id="6071b-120">-Runspace</span></span>

<span data-ttu-id="6071b-121">Um ou mais objetos de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="6071b-121">One or more **Runspace** objects to be disabled.</span></span>

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

### <span data-ttu-id="6071b-122">-RunspaceId</span><span class="sxs-lookup"><span data-stu-id="6071b-122">-RunspaceId</span></span>

<span data-ttu-id="6071b-123">Um ou mais números de ID de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="6071b-123">One or more **Runspace** Id numbers to be disabled.</span></span>

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

### <span data-ttu-id="6071b-124">-RunspaceInstanceId</span><span class="sxs-lookup"><span data-stu-id="6071b-124">-RunspaceInstanceId</span></span>

<span data-ttu-id="6071b-125">Um ou mais GUIDs de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="6071b-125">One or more **Runspace** GUIDs to be disabled.</span></span>

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

### <span data-ttu-id="6071b-126">-RunspaceName</span><span class="sxs-lookup"><span data-stu-id="6071b-126">-RunspaceName</span></span>

<span data-ttu-id="6071b-127">Um ou mais nomes de **runspace** a serem desabilitados.</span><span class="sxs-lookup"><span data-stu-id="6071b-127">One or more **Runspace** names to be disabled.</span></span>

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

### <span data-ttu-id="6071b-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6071b-128">CommonParameters</span></span>

<span data-ttu-id="6071b-129">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6071b-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6071b-130">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6071b-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6071b-131">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="6071b-131">INPUTS</span></span>

## <span data-ttu-id="6071b-132">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="6071b-132">OUTPUTS</span></span>

## <span data-ttu-id="6071b-133">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="6071b-133">NOTES</span></span>

## <span data-ttu-id="6071b-134">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="6071b-134">RELATED LINKS</span></span>

[<span data-ttu-id="6071b-135">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="6071b-135">Enable-RunspaceDebug</span></span>](Enable-RunspaceDebug.md)

[<span data-ttu-id="6071b-136">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="6071b-136">Get-RunspaceDebug</span></span>](Get-RunspaceDebug.md)

