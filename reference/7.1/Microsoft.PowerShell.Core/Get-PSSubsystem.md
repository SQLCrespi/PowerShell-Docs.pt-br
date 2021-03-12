---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 10/15/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssubsystem?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSubsystem
ms.openlocfilehash: 1e08715562ab5a5b52193dacdd2c48cacb4540e8
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103195525"
---
# <span data-ttu-id="c3d4b-102">Get-PSSubsystem</span><span class="sxs-lookup"><span data-stu-id="c3d4b-102">Get-PSSubsystem</span></span>

## <span data-ttu-id="c3d4b-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="c3d4b-103">SYNOPSIS</span></span>
<span data-ttu-id="c3d4b-104">Recupera informações sobre os subsistemas registrados no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3d4b-104">Retrieves information about the subsystems registered in PowerShell.</span></span>

## <span data-ttu-id="c3d4b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c3d4b-105">SYNTAX</span></span>

### <span data-ttu-id="c3d4b-106">GetAllSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="c3d4b-106">GetAllSet (Default)</span></span>

```
Get-PSSubsystem [<CommonParameters>]
```

### <span data-ttu-id="c3d4b-107">GetByKindSet</span><span class="sxs-lookup"><span data-stu-id="c3d4b-107">GetByKindSet</span></span>

```
Get-PSSubsystem -Kind <SubsystemKind> [<CommonParameters>]
```

### <span data-ttu-id="c3d4b-108">GetByTypeSet</span><span class="sxs-lookup"><span data-stu-id="c3d4b-108">GetByTypeSet</span></span>

```
Get-PSSubsystem -SubsystemType <Type> [<CommonParameters>]
```

## <span data-ttu-id="c3d4b-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c3d4b-109">DESCRIPTION</span></span>

<span data-ttu-id="c3d4b-110">Recupera informações sobre os subsistemas registrados no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3d4b-110">Retrieves information about the subsystems registered in PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="c3d4b-111">Esse é um recurso experimental.</span><span class="sxs-lookup"><span data-stu-id="c3d4b-111">This is an experimental feature.</span></span> <span data-ttu-id="c3d4b-112">Esse cmdlet só está disponível quando o `PSSubsystemPluginModel` recurso está habilitado.</span><span class="sxs-lookup"><span data-stu-id="c3d4b-112">This cmdlet is only available when the `PSSubsystemPluginModel` feature is enabled.</span></span> <span data-ttu-id="c3d4b-113">Para mais informações, confira [Usar recursos experimentais](/powershell/scripting/learn/experimental-features).</span><span class="sxs-lookup"><span data-stu-id="c3d4b-113">For more information, see [Using Experimental Features](/powershell/scripting/learn/experimental-features).</span></span>

<span data-ttu-id="c3d4b-114">Ele possibilita a separação dos componentes de `System.Management.Automation.dll` em subsistemas individuais que residem no próprio assembly.</span><span class="sxs-lookup"><span data-stu-id="c3d4b-114">The feature makes it possible to separate components of `System.Management.Automation.dll` into individual subsystems that reside in their own assembly.</span></span> <span data-ttu-id="c3d4b-115">Essa divisão reduz o volume de disco do mecanismo principal do PowerShell e permite que esses componentes se tornem recursos opcionais para uma instalação mínima do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3d4b-115">This separation reduces the disk footprint of the core PowerShell engine and allows these components to become optional features for a minimal PowerShell installation.</span></span>

<span data-ttu-id="c3d4b-116">Atualmente, há suporte apenas para o subsistema **CommandPredictor**.</span><span class="sxs-lookup"><span data-stu-id="c3d4b-116">Currently, only the **CommandPredictor** subsystem is supported.</span></span> <span data-ttu-id="c3d4b-117">Esse subsistema é usado com o módulo PSReadLine para fornecer plug-ins de previsão personalizados.</span><span class="sxs-lookup"><span data-stu-id="c3d4b-117">This subsystem is used along with the PSReadLine module to provide custom prediction plugins.</span></span> <span data-ttu-id="c3d4b-118">No futuro, será possível dividir **Job**, **CommandCompleter**, **Remoting** e outros componentes em assemblies de subsistema fora do `System.Management.Automation.dll`.</span><span class="sxs-lookup"><span data-stu-id="c3d4b-118">In future, **Job**, **CommandCompleter**, **Remoting** and other components could be separated into subsystem assemblies outside of `System.Management.Automation.dll`.</span></span>

## <span data-ttu-id="c3d4b-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="c3d4b-119">EXAMPLES</span></span>

### <span data-ttu-id="c3d4b-120">Exemplo 1-exibir todos os subsistemas disponíveis</span><span class="sxs-lookup"><span data-stu-id="c3d4b-120">Example 1 - Display all available subsystems</span></span>

```powershell
Get-PSSubsystem
```

```Output
Kind              SubsystemType     IsRegistered Implementations
----              -------------     ------------ ---------------
CommandPredictor  ICommandPredictor        False {}
```

### <span data-ttu-id="c3d4b-121">Exemplo 2-exibir todos os subsistemas disponíveis de um tipo específico</span><span class="sxs-lookup"><span data-stu-id="c3d4b-121">Example 2 - Display all available subsystems of a specific kind</span></span>

```powershell
PS> Get-PSSubsystem -Kind CommandPredictor | Format-List
```

```Output
Kind                      : CommandPredictor
SubsystemType             : System.Management.Automation.Subsystem.ICommandPredictor
AllowUnregistration       : True
AllowMultipleRegistration : True
RequiredCmdlets           : {}
RequiredFunctions         : {}
IsRegistered              : False
Implementations           : {}
```

## <span data-ttu-id="c3d4b-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c3d4b-122">PARAMETERS</span></span>

### <span data-ttu-id="c3d4b-123">-Tipo</span><span class="sxs-lookup"><span data-stu-id="c3d4b-123">-Kind</span></span>


<span data-ttu-id="c3d4b-124">Especifica o tipo de subsistema a ser retornado.</span><span class="sxs-lookup"><span data-stu-id="c3d4b-124">Specifies the kind of subsystem to be returned.</span></span> <span data-ttu-id="c3d4b-125">Os valores válidos são: `CommandPredictor` .</span><span class="sxs-lookup"><span data-stu-id="c3d4b-125">Valid values are: `CommandPredictor`.</span></span>

```yaml
Type: System.Management.Automation.Subsystem.SubsystemKind
Parameter Sets: GetByKindSet
Aliases:
Accepted values: CommandPredictor

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c3d4b-126">-Subsistematype</span><span class="sxs-lookup"><span data-stu-id="c3d4b-126">-SubsystemType</span></span>

<span data-ttu-id="c3d4b-127">Especifica o tipo de subsistema a ser retornado.</span><span class="sxs-lookup"><span data-stu-id="c3d4b-127">Specifies the type of subsystem to be returned.</span></span>

```yaml
Type: System.Type
Parameter Sets: GetByTypeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c3d4b-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c3d4b-128">CommonParameters</span></span>

<span data-ttu-id="c3d4b-129">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c3d4b-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c3d4b-130">Para obter mais informações, confira [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c3d4b-130">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c3d4b-131">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="c3d4b-131">INPUTS</span></span>

### <span data-ttu-id="c3d4b-132">System. Management. Automation. Subsystem. SubsystemKind</span><span class="sxs-lookup"><span data-stu-id="c3d4b-132">System.Management.Automation.Subsystem.SubsystemKind</span></span>

### <span data-ttu-id="c3d4b-133">System.Type</span><span class="sxs-lookup"><span data-stu-id="c3d4b-133">System.Type</span></span>

## <span data-ttu-id="c3d4b-134">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="c3d4b-134">OUTPUTS</span></span>

### <span data-ttu-id="c3d4b-135">System. Management. Automation. Subsystem. SubsystemInfo</span><span class="sxs-lookup"><span data-stu-id="c3d4b-135">System.Management.Automation.Subsystem.SubsystemInfo</span></span>

## <span data-ttu-id="c3d4b-136">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="c3d4b-136">NOTES</span></span>

## <span data-ttu-id="c3d4b-137">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="c3d4b-137">RELATED LINKS</span></span>

[<span data-ttu-id="c3d4b-138">about_experimental_features</span><span class="sxs-lookup"><span data-stu-id="c3d4b-138">about_experimental_features</span></span>](about/about_experimental_features.md)

[<span data-ttu-id="c3d4b-139">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="c3d4b-139">Disable-ExperimentalFeature</span></span>](Disable-ExperimentalFeature.md)

[<span data-ttu-id="c3d4b-140">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="c3d4b-140">Enable-ExperimentalFeature</span></span>](Get-ExperimentalFeature.md)

[<span data-ttu-id="c3d4b-141">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="c3d4b-141">Get-ExperimentalFeature</span></span>](Get-ExperimentalFeature.md)

[<span data-ttu-id="c3d4b-142">Usar recursos experimentais</span><span class="sxs-lookup"><span data-stu-id="c3d4b-142">Using Experimental Features</span></span>](/powershell/scripting/learn/experimental-features)
