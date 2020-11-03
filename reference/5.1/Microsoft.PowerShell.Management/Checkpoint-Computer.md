---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/checkpoint-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Checkpoint-Computer
ms.openlocfilehash: 61f8d626cd45cfe47f0e65a3043696a01c97ca20
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194218"
---
# <span data-ttu-id="e7d89-103">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="e7d89-103">Checkpoint-Computer</span></span>

## <span data-ttu-id="e7d89-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="e7d89-104">SYNOPSIS</span></span>
<span data-ttu-id="e7d89-105">Cria um ponto de restauração do sistema no computador local.</span><span class="sxs-lookup"><span data-stu-id="e7d89-105">Creates a system restore point on the local computer.</span></span>

## <span data-ttu-id="e7d89-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e7d89-106">SYNTAX</span></span>

```
Checkpoint-Computer [-Description] <String> [[-RestorePointType] <String>] [<CommonParameters>]
```

## <span data-ttu-id="e7d89-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e7d89-107">DESCRIPTION</span></span>

<span data-ttu-id="e7d89-108">O `Checkpoint-Computer` cmdlet cria um ponto de restauração do sistema no computador local.</span><span class="sxs-lookup"><span data-stu-id="e7d89-108">The `Checkpoint-Computer` cmdlet creates a system restore point on the local computer.</span></span>

<span data-ttu-id="e7d89-109">Os pontos de restauração do sistema e o `Checkpoint-Computer` cmdlet têm suporte apenas em sistemas operacionais cliente, como o Windows 8, o Windows 7, o Windows Vista e o Windows XP.</span><span class="sxs-lookup"><span data-stu-id="e7d89-109">System restore points and the `Checkpoint-Computer` cmdlet are supported only on client operating systems, such as Windows 8, Windows 7, Windows Vista, and Windows XP.</span></span>

<span data-ttu-id="e7d89-110">A partir do Windows 8, `Checkpoint-Computer` não é possível criar mais de um ponto de verificação por dia.</span><span class="sxs-lookup"><span data-stu-id="e7d89-110">Beginning in Windows 8, `Checkpoint-Computer` cannot create more than one checkpoint each day.</span></span>

## <span data-ttu-id="e7d89-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e7d89-111">EXAMPLES</span></span>

### <span data-ttu-id="e7d89-112">Exemplo 1: criar um ponto de restauração do sistema</span><span class="sxs-lookup"><span data-stu-id="e7d89-112">Example 1: Create a system restore point</span></span>

```powershell
Checkpoint-Computer -Description "Install MyApp"
```

<span data-ttu-id="e7d89-113">Este comando cria um ponto de restauração do sistema chamado Install MyApp.</span><span class="sxs-lookup"><span data-stu-id="e7d89-113">This command creates a system restore point called Install MyApp.</span></span>
<span data-ttu-id="e7d89-114">Ele utiliza o tipo de ponto de restauração de APPLICATION_INSTALL padrão.</span><span class="sxs-lookup"><span data-stu-id="e7d89-114">It uses the default APPLICATION_INSTALL restore point type.</span></span>

### <span data-ttu-id="e7d89-115">Exemplo 2: criar um ponto de restauração do sistema MODIFY_SETTINGS</span><span class="sxs-lookup"><span data-stu-id="e7d89-115">Example 2: Create a system MODIFY_SETTINGS restore point</span></span>

```powershell
Checkpoint-Computer -Description "ChangeNetSettings" -RestorePointType MODIFY_SETTINGS
```

<span data-ttu-id="e7d89-116">Este comando cria um ponto de restauração do sistema MODIFY_SETTINGS chamado "ChangeNetSettings".</span><span class="sxs-lookup"><span data-stu-id="e7d89-116">This command creates a MODIFY_SETTINGS system restore point called "ChangeNetSettings".</span></span>

## <span data-ttu-id="e7d89-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e7d89-117">PARAMETERS</span></span>

### <span data-ttu-id="e7d89-118">-Description</span><span class="sxs-lookup"><span data-stu-id="e7d89-118">-Description</span></span>

<span data-ttu-id="e7d89-119">Especifica um nome descritivo para o ponto de restauração.</span><span class="sxs-lookup"><span data-stu-id="e7d89-119">Specifies a descriptive name for the restore point.</span></span>
<span data-ttu-id="e7d89-120">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="e7d89-120">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e7d89-121">-RestorePointType</span><span class="sxs-lookup"><span data-stu-id="e7d89-121">-RestorePointType</span></span>

<span data-ttu-id="e7d89-122">Especifica o tipo de ponto de restauração.</span><span class="sxs-lookup"><span data-stu-id="e7d89-122">Specifies the type of restore point.</span></span>
<span data-ttu-id="e7d89-123">O padrão é APPLICATION_INSTALL.</span><span class="sxs-lookup"><span data-stu-id="e7d89-123">The default is APPLICATION_INSTALL.</span></span>

<span data-ttu-id="e7d89-124">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="e7d89-124">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="e7d89-125">APPLICATION_INSTALL</span><span class="sxs-lookup"><span data-stu-id="e7d89-125">APPLICATION_INSTALL</span></span>
- <span data-ttu-id="e7d89-126">APPLICATION_UNINSTALL</span><span class="sxs-lookup"><span data-stu-id="e7d89-126">APPLICATION_UNINSTALL</span></span>
- <span data-ttu-id="e7d89-127">DEVICE_DRIVER_INSTALL</span><span class="sxs-lookup"><span data-stu-id="e7d89-127">DEVICE_DRIVER_INSTALL</span></span>
- <span data-ttu-id="e7d89-128">MODIFY_SETTINGS</span><span class="sxs-lookup"><span data-stu-id="e7d89-128">MODIFY_SETTINGS</span></span>
- <span data-ttu-id="e7d89-129">CANCELLED_OPERATION</span><span class="sxs-lookup"><span data-stu-id="e7d89-129">CANCELLED_OPERATION</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: RPT
Accepted values: APPLICATION_INSTALL, APPLICATION_UNINSTALL, DEVICE_DRIVER_INSTALL, MODIFY_SETTINGS, CANCELLED_OPERATION

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e7d89-130">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e7d89-130">CommonParameters</span></span>

<span data-ttu-id="e7d89-131">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e7d89-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e7d89-132">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="e7d89-132">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="e7d89-133">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="e7d89-133">INPUTS</span></span>

### <span data-ttu-id="e7d89-134">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e7d89-134">None</span></span>

<span data-ttu-id="e7d89-135">Não é possível canalizar objetos para `Checkpoint-Computer` .</span><span class="sxs-lookup"><span data-stu-id="e7d89-135">You cannot pipe objects to `Checkpoint-Computer`.</span></span>

## <span data-ttu-id="e7d89-136">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="e7d89-136">OUTPUTS</span></span>

### <span data-ttu-id="e7d89-137">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e7d89-137">None</span></span>

<span data-ttu-id="e7d89-138">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="e7d89-138">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e7d89-139">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e7d89-139">NOTES</span></span>

- <span data-ttu-id="e7d89-140">Esse cmdlet usa o método **CreateRestorePoint** da classe **SystemRestore** com um evento **BEGIN_SYSTEM_CHANGE** .</span><span class="sxs-lookup"><span data-stu-id="e7d89-140">This cmdlet uses the **CreateRestorePoint** method of the **SystemRestore** class with a **BEGIN_SYSTEM_CHANGE** event.</span></span>
- <span data-ttu-id="e7d89-141">A partir do Windows 8, o `Checkpoint-Computer` não pode criar mais de um ponto de restauração do sistema por dia.</span><span class="sxs-lookup"><span data-stu-id="e7d89-141">Beginning in Windows 8, `Checkpoint-Computer` cannot create more than one system restore point each day.</span></span> <span data-ttu-id="e7d89-142">Se você tentar criar um novo ponto de restauração antes do período de 24 horas, o Windows PowerShell gera o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="e7d89-142">If you try to create a new restore point before the 24-hour period has elapsed, Windows PowerShell generates the following error:</span></span>

  `"A new system restore point cannot be created because one has already been created within the past 24 hours.
  Please try again later."`

## <span data-ttu-id="e7d89-143">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e7d89-143">RELATED LINKS</span></span>

[<span data-ttu-id="e7d89-144">Disable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="e7d89-144">Disable-ComputerRestore</span></span>](Disable-ComputerRestore.md)

[<span data-ttu-id="e7d89-145">Enable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="e7d89-145">Enable-ComputerRestore</span></span>](Enable-ComputerRestore.md)

[<span data-ttu-id="e7d89-146">Get-ComputerRestorePoint</span><span class="sxs-lookup"><span data-stu-id="e7d89-146">Get-ComputerRestorePoint</span></span>](Get-ComputerRestorePoint.md)

[<span data-ttu-id="e7d89-147">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="e7d89-147">Restore-Computer</span></span>](Restore-Computer.md)
