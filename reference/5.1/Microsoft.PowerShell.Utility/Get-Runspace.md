---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-runspace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Runspace
ms.openlocfilehash: fb1076e7bb0843fe7208d00e51e19063c27dfa68
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193801"
---
# <span data-ttu-id="d054f-103">Get-Runspace</span><span class="sxs-lookup"><span data-stu-id="d054f-103">Get-Runspace</span></span>

## <span data-ttu-id="d054f-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d054f-104">SYNOPSIS</span></span>
<span data-ttu-id="d054f-105">Obtém Runspaces ativos em um processo de host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d054f-105">Gets active runspaces within a PowerShell host process.</span></span>

## <span data-ttu-id="d054f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d054f-106">SYNTAX</span></span>

### <span data-ttu-id="d054f-107">NameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="d054f-107">NameParameterSet (Default)</span></span>

```
Get-Runspace [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="d054f-108">IdParameterSet</span><span class="sxs-lookup"><span data-stu-id="d054f-108">IdParameterSet</span></span>

```
Get-Runspace [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="d054f-109">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="d054f-109">InstanceIdParameterSet</span></span>

```
Get-Runspace [-InstanceId] <Guid[]> [<CommonParameters>]
```

## <span data-ttu-id="d054f-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d054f-110">DESCRIPTION</span></span>

<span data-ttu-id="d054f-111">O `Get-Runspace` cmdlet obtém Runspaces ativos em um processo de host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d054f-111">The `Get-Runspace` cmdlet gets active runspaces in a PowerShell host process.</span></span>

## <span data-ttu-id="d054f-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d054f-112">EXAMPLES</span></span>

### <span data-ttu-id="d054f-113">Exemplo 1: obter Runspaces</span><span class="sxs-lookup"><span data-stu-id="d054f-113">Example 1: Get runspaces</span></span>

```powershell
Get-Runspace
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  1 Runspace1       localhost       Local         Opened        Busy
  2 Runspace2       localhost       Local         Opened        Available
  3 Runspace3       localhost       Local         Opened        Available
```

### <span data-ttu-id="d054f-114">Exemplo 2: obter runspace por ID</span><span class="sxs-lookup"><span data-stu-id="d054f-114">Example 2: Get runspace by Id</span></span>

```powershell
Get-Runspace -Id 2
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  2 Runspace2       localhost       Local         Opened        Available
```

### <span data-ttu-id="d054f-115">Exemplo 3: obter runspace por nome</span><span class="sxs-lookup"><span data-stu-id="d054f-115">Example 3: Get runspace by Name</span></span>

```powershell
Get-Runspace -Name Runspace1
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  1 Runspace1       localhost       Local         Opened        Busy
```

### <span data-ttu-id="d054f-116">Exemplo 4: obter o runspace por InstanceId</span><span class="sxs-lookup"><span data-stu-id="d054f-116">Example 4: Get runspace by InstanceId</span></span>

<span data-ttu-id="d054f-117">Neste exemplo, identificamos um runspace disponível usando o `Name` parâmetro e armazenamos o objeto de retorno na variável `$activeRunspace` .</span><span class="sxs-lookup"><span data-stu-id="d054f-117">In this example, we identify an available runspace using the `Name` parameter and store the return object to the variable `$activeRunspace`.</span></span> <span data-ttu-id="d054f-118">Isso permite que você use as propriedades do **runspace** em execuções subsequentes do `Get-Runspace` .</span><span class="sxs-lookup"><span data-stu-id="d054f-118">This allows you to use the properties of the **Runspace** in subsequent runs of `Get-Runspace`.</span></span>

```powershell
$activeRunspace = Get-Runspace -Name Runspace1
Get-Runspace -InstanceId $activeRunspace.InstanceId
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  1 Runspace1       localhost       Local         Opened        Busy
```

## <span data-ttu-id="d054f-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d054f-119">PARAMETERS</span></span>

### <span data-ttu-id="d054f-120">-Id</span><span class="sxs-lookup"><span data-stu-id="d054f-120">-Id</span></span>

<span data-ttu-id="d054f-121">Especifica a ID de um runspace</span><span class="sxs-lookup"><span data-stu-id="d054f-121">Specifies the Id of a runspace</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: IdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d054f-122">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="d054f-122">-InstanceId</span></span>

<span data-ttu-id="d054f-123">Especifica o GUID de ID de instância de um trabalho em execução.</span><span class="sxs-lookup"><span data-stu-id="d054f-123">Specifies the instance ID GUID of a running job.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d054f-124">-Name</span><span class="sxs-lookup"><span data-stu-id="d054f-124">-Name</span></span>

<span data-ttu-id="d054f-125">Especifica o nome de um runspace</span><span class="sxs-lookup"><span data-stu-id="d054f-125">Specifies the Name of a runspace</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d054f-126">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d054f-126">CommonParameters</span></span>

<span data-ttu-id="d054f-127">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d054f-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d054f-128">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d054f-128">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d054f-129">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d054f-129">INPUTS</span></span>

## <span data-ttu-id="d054f-130">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d054f-130">OUTPUTS</span></span>

### <span data-ttu-id="d054f-131">System. Management. Automation. Runspaces. runspace</span><span class="sxs-lookup"><span data-stu-id="d054f-131">System.Management.Automation.Runspaces.Runspace</span></span>

<span data-ttu-id="d054f-132">Você pode canalizar os resultados de um `Get-Runspace` comando para `Debug-Runspace` .</span><span class="sxs-lookup"><span data-stu-id="d054f-132">You can pipe the results of a `Get-Runspace` command to `Debug-Runspace`.</span></span>

## <span data-ttu-id="d054f-133">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d054f-133">NOTES</span></span>

## <span data-ttu-id="d054f-134">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d054f-134">RELATED LINKS</span></span>

[<span data-ttu-id="d054f-135">Debug-Runspace</span><span class="sxs-lookup"><span data-stu-id="d054f-135">Debug-Runspace</span></span>](Debug-Runspace.md)
