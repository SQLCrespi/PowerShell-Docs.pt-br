---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-runspace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Runspace
ms.openlocfilehash: 34843894cb6253e3d8e89072cf79cb9237d4fc19
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597208"
---
# <span data-ttu-id="10cc2-102">Get-Runspace</span><span class="sxs-lookup"><span data-stu-id="10cc2-102">Get-Runspace</span></span>

## <span data-ttu-id="10cc2-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="10cc2-103">SYNOPSIS</span></span>
<span data-ttu-id="10cc2-104">Obtém Runspaces ativos em um processo de host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="10cc2-104">Gets active runspaces within a PowerShell host process.</span></span>

## <span data-ttu-id="10cc2-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="10cc2-105">SYNTAX</span></span>

### <span data-ttu-id="10cc2-106">NameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="10cc2-106">NameParameterSet (Default)</span></span>

```
Get-Runspace [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="10cc2-107">IdParameterSet</span><span class="sxs-lookup"><span data-stu-id="10cc2-107">IdParameterSet</span></span>

```
Get-Runspace [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="10cc2-108">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="10cc2-108">InstanceIdParameterSet</span></span>

```
Get-Runspace [-InstanceId] <Guid[]> [<CommonParameters>]
```

## <span data-ttu-id="10cc2-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="10cc2-109">DESCRIPTION</span></span>

<span data-ttu-id="10cc2-110">O `Get-Runspace` cmdlet obtém Runspaces ativos em um processo de host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="10cc2-110">The `Get-Runspace` cmdlet gets active runspaces in a PowerShell host process.</span></span>

## <span data-ttu-id="10cc2-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="10cc2-111">EXAMPLES</span></span>

### <span data-ttu-id="10cc2-112">Exemplo 1: obter Runspaces</span><span class="sxs-lookup"><span data-stu-id="10cc2-112">Example 1: Get runspaces</span></span>

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

### <span data-ttu-id="10cc2-113">Exemplo 2: obter runspace por ID</span><span class="sxs-lookup"><span data-stu-id="10cc2-113">Example 2: Get runspace by Id</span></span>

```powershell
Get-Runspace -Id 2
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  2 Runspace2       localhost       Local         Opened        Available
```

### <span data-ttu-id="10cc2-114">Exemplo 3: obter runspace por nome</span><span class="sxs-lookup"><span data-stu-id="10cc2-114">Example 3: Get runspace by Name</span></span>

```powershell
Get-Runspace -Name Runspace1
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  1 Runspace1       localhost       Local         Opened        Busy
```

### <span data-ttu-id="10cc2-115">Exemplo 4: obter o runspace por InstanceId</span><span class="sxs-lookup"><span data-stu-id="10cc2-115">Example 4: Get runspace by InstanceId</span></span>

<span data-ttu-id="10cc2-116">Neste exemplo, identificamos um runspace disponível usando o `Name` parâmetro e armazenamos o objeto de retorno na variável `$activeRunspace` .</span><span class="sxs-lookup"><span data-stu-id="10cc2-116">In this example, we identify an available runspace using the `Name` parameter and store the return object to the variable `$activeRunspace`.</span></span> <span data-ttu-id="10cc2-117">Isso permite que você use as propriedades do **runspace** em execuções subsequentes do `Get-Runspace` .</span><span class="sxs-lookup"><span data-stu-id="10cc2-117">This allows you to use the properties of the **Runspace** in subsequent runs of `Get-Runspace`.</span></span>

```powershell
$activeRunspace = Get-Runspace -Name Runspace1
Get-Runspace -InstanceId $activeRunspace.InstanceId
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  1 Runspace1       localhost       Local         Opened        Busy
```

## <span data-ttu-id="10cc2-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="10cc2-118">PARAMETERS</span></span>

### <span data-ttu-id="10cc2-119">-Id</span><span class="sxs-lookup"><span data-stu-id="10cc2-119">-Id</span></span>

<span data-ttu-id="10cc2-120">Especifica a ID de um runspace</span><span class="sxs-lookup"><span data-stu-id="10cc2-120">Specifies the Id of a runspace</span></span>

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

### <span data-ttu-id="10cc2-121">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="10cc2-121">-InstanceId</span></span>

<span data-ttu-id="10cc2-122">Especifica o GUID de ID de instância de um trabalho em execução.</span><span class="sxs-lookup"><span data-stu-id="10cc2-122">Specifies the instance ID GUID of a running job.</span></span>

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

### <span data-ttu-id="10cc2-123">-Name</span><span class="sxs-lookup"><span data-stu-id="10cc2-123">-Name</span></span>

<span data-ttu-id="10cc2-124">Especifica o nome de um runspace</span><span class="sxs-lookup"><span data-stu-id="10cc2-124">Specifies the Name of a runspace</span></span>

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

### <span data-ttu-id="10cc2-125">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="10cc2-125">CommonParameters</span></span>

<span data-ttu-id="10cc2-126">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="10cc2-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="10cc2-127">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="10cc2-127">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="10cc2-128">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="10cc2-128">INPUTS</span></span>

## <span data-ttu-id="10cc2-129">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="10cc2-129">OUTPUTS</span></span>

### <span data-ttu-id="10cc2-130">System. Management. Automation. Runspaces. runspace</span><span class="sxs-lookup"><span data-stu-id="10cc2-130">System.Management.Automation.Runspaces.Runspace</span></span>

<span data-ttu-id="10cc2-131">Você pode canalizar os resultados de um `Get-Runspace` comando para `Debug-Runspace` .</span><span class="sxs-lookup"><span data-stu-id="10cc2-131">You can pipe the results of a `Get-Runspace` command to `Debug-Runspace`.</span></span>

## <span data-ttu-id="10cc2-132">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="10cc2-132">NOTES</span></span>

## <span data-ttu-id="10cc2-133">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="10cc2-133">RELATED LINKS</span></span>

[<span data-ttu-id="10cc2-134">Debug-Runspace</span><span class="sxs-lookup"><span data-stu-id="10cc2-134">Debug-Runspace</span></span>](Debug-Runspace.md)

