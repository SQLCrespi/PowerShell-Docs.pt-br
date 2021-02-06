---
external help file: System.Management.Automation.dll-Help.xml
Module Name: Microsoft.PowerShell.Core
ms.date: 10/15/2020
schema: 2.0.0
ms.openlocfilehash: 5cb8ddbd06f8b7fdbadae0b7c738e26a68ff5c48
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595596"
---
# <span data-ttu-id="465a5-101">Get-PSSubsystem</span><span class="sxs-lookup"><span data-stu-id="465a5-101">Get-PSSubsystem</span></span>

## <span data-ttu-id="465a5-102">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="465a5-102">SYNOPSIS</span></span>
<span data-ttu-id="465a5-103">Recupera informações sobre os subsistemas registrados no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="465a5-103">Retrieves information about the subsystems registered in PowerShell.</span></span>

## <span data-ttu-id="465a5-104">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="465a5-104">SYNTAX</span></span>

### <span data-ttu-id="465a5-105">GetAllSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="465a5-105">GetAllSet (Default)</span></span>

```
Get-PSSubsystem [<CommonParameters>]
```

### <span data-ttu-id="465a5-106">GetByKindSet</span><span class="sxs-lookup"><span data-stu-id="465a5-106">GetByKindSet</span></span>

```
Get-PSSubsystem -Kind <SubsystemKind> [<CommonParameters>]
```

### <span data-ttu-id="465a5-107">GetByTypeSet</span><span class="sxs-lookup"><span data-stu-id="465a5-107">GetByTypeSet</span></span>

```
Get-PSSubsystem -SubsystemType <Type> [<CommonParameters>]
```

## <span data-ttu-id="465a5-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="465a5-108">DESCRIPTION</span></span>

<span data-ttu-id="465a5-109">Recupera informações sobre os subsistemas registrados no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="465a5-109">Retrieves information about the subsystems registered in PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="465a5-110">Esse é um recurso experimental.</span><span class="sxs-lookup"><span data-stu-id="465a5-110">This is an experimental feature.</span></span> <span data-ttu-id="465a5-111">Esse cmdlet só está disponível quando o `PSSubsystemPluginModel` recurso está habilitado.</span><span class="sxs-lookup"><span data-stu-id="465a5-111">This cmdlet is only available when the `PSSubsystemPluginModel` feature is enabled.</span></span> <span data-ttu-id="465a5-112">Para mais informações, confira [Usar recursos experimentais](/powershell/scripting/learn/experimental-features).</span><span class="sxs-lookup"><span data-stu-id="465a5-112">For more information, see [Using Experimental Features](/powershell/scripting/learn/experimental-features).</span></span>

<span data-ttu-id="465a5-113">Ele possibilita a separação dos componentes de `System.Management.Automation.dll` em subsistemas individuais que residem no próprio assembly.</span><span class="sxs-lookup"><span data-stu-id="465a5-113">The feature makes it possible to separate components of `System.Management.Automation.dll` into individual subsystems that reside in their own assembly.</span></span> <span data-ttu-id="465a5-114">Essa divisão reduz o volume de disco do mecanismo principal do PowerShell e permite que esses componentes se tornem recursos opcionais para uma instalação mínima do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="465a5-114">This separation reduces the disk footprint of the core PowerShell engine and allows these components to become optional features for a minimal PowerShell installation.</span></span>

<span data-ttu-id="465a5-115">Atualmente, há suporte apenas para o subsistema **CommandPredictor**.</span><span class="sxs-lookup"><span data-stu-id="465a5-115">Currently, only the **CommandPredictor** subsystem is supported.</span></span> <span data-ttu-id="465a5-116">Esse subsistema é usado com o módulo PSReadLine para fornecer plug-ins de previsão personalizados.</span><span class="sxs-lookup"><span data-stu-id="465a5-116">This subsystem is used along with the PSReadLine module to provide custom prediction plugins.</span></span> <span data-ttu-id="465a5-117">No futuro, será possível dividir **Job**, **CommandCompleter**, **Remoting** e outros componentes em assemblies de subsistema fora do `System.Management.Automation.dll`.</span><span class="sxs-lookup"><span data-stu-id="465a5-117">In future, **Job**, **CommandCompleter**, **Remoting** and other components could be separated into subsystem assemblies outside of `System.Management.Automation.dll`.</span></span>

## <span data-ttu-id="465a5-118">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="465a5-118">EXAMPLES</span></span>

### <span data-ttu-id="465a5-119">Exemplo 1-exibir todos os subsistemas disponíveis</span><span class="sxs-lookup"><span data-stu-id="465a5-119">Example 1 - Display all available subsystems</span></span>

```powershell
Get-PSSubsystem
```

```Output
Kind              SubsystemType     IsRegistered Implementations
----              -------------     ------------ ---------------
CommandPredictor  ICommandPredictor        False {}
```

### <span data-ttu-id="465a5-120">Exemplo 2-exibir todos os subsistemas disponíveis de um tipo específico</span><span class="sxs-lookup"><span data-stu-id="465a5-120">Example 2 - Display all available subsystems of a specific kind</span></span>

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

## <span data-ttu-id="465a5-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="465a5-121">PARAMETERS</span></span>

### <span data-ttu-id="465a5-122">-Tipo</span><span class="sxs-lookup"><span data-stu-id="465a5-122">-Kind</span></span>


<span data-ttu-id="465a5-123">Especifica o tipo de subsistema a ser retornado.</span><span class="sxs-lookup"><span data-stu-id="465a5-123">Specifies the kind of subsystem to be returned.</span></span> <span data-ttu-id="465a5-124">Os valores válidos são: `CommandPredictor` .</span><span class="sxs-lookup"><span data-stu-id="465a5-124">Valid values are: `CommandPredictor`.</span></span>

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

### <span data-ttu-id="465a5-125">-Subsistematype</span><span class="sxs-lookup"><span data-stu-id="465a5-125">-SubsystemType</span></span>

<span data-ttu-id="465a5-126">Especifica o tipo de subsistema a ser retornado.</span><span class="sxs-lookup"><span data-stu-id="465a5-126">Specifies the type of subsystem to be returned.</span></span>

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

### <span data-ttu-id="465a5-127">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="465a5-127">CommonParameters</span></span>

<span data-ttu-id="465a5-128">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="465a5-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="465a5-129">Para obter mais informações, confira [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="465a5-129">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="465a5-130">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="465a5-130">INPUTS</span></span>

### <span data-ttu-id="465a5-131">System. Management. Automation. Subsystem. SubsystemKind</span><span class="sxs-lookup"><span data-stu-id="465a5-131">System.Management.Automation.Subsystem.SubsystemKind</span></span>

### <span data-ttu-id="465a5-132">System.Type</span><span class="sxs-lookup"><span data-stu-id="465a5-132">System.Type</span></span>

## <span data-ttu-id="465a5-133">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="465a5-133">OUTPUTS</span></span>

### <span data-ttu-id="465a5-134">System. Management. Automation. Subsystem. SubsystemInfo</span><span class="sxs-lookup"><span data-stu-id="465a5-134">System.Management.Automation.Subsystem.SubsystemInfo</span></span>

## <span data-ttu-id="465a5-135">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="465a5-135">NOTES</span></span>

## <span data-ttu-id="465a5-136">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="465a5-136">RELATED LINKS</span></span>

[<span data-ttu-id="465a5-137">about_experimental_features</span><span class="sxs-lookup"><span data-stu-id="465a5-137">about_experimental_features</span></span>](about/about_experimental_features.md)

[<span data-ttu-id="465a5-138">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="465a5-138">Disable-ExperimentalFeature</span></span>](Disable-ExperimentalFeature.md)

[<span data-ttu-id="465a5-139">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="465a5-139">Enable-ExperimentalFeature</span></span>](Get-ExperimentalFeature.md)

[<span data-ttu-id="465a5-140">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="465a5-140">Get-ExperimentalFeature</span></span>](Get-ExperimentalFeature.md)

[<span data-ttu-id="465a5-141">Usar recursos experimentais</span><span class="sxs-lookup"><span data-stu-id="465a5-141">Using Experimental Features</span></span>](/powershell/scripting/learn/experimental-features)
