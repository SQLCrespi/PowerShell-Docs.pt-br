---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
ms.openlocfilehash: 64a00e041bbeeea117db43116b486e83dfe923b0
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085823"
---
# <a name="new-built-in-dsc-resources"></a><span data-ttu-id="d1146-102">Novos recursos internos do DSC</span><span class="sxs-lookup"><span data-stu-id="d1146-102">New built-in DSC resources</span></span>

<span data-ttu-id="d1146-103">O WMF 5.0 RTM tem quatro novos recursos do DSC:</span><span class="sxs-lookup"><span data-stu-id="d1146-103">WMF 5.0 RTM has 4 new DSC resources:</span></span>
* <span data-ttu-id="d1146-104">WindowsFeatureSet</span><span class="sxs-lookup"><span data-stu-id="d1146-104">WindowsFeatureSet</span></span>
* <span data-ttu-id="d1146-105">WindowsOptionalFeatureSet</span><span class="sxs-lookup"><span data-stu-id="d1146-105">WindowsOptionalFeatureSet</span></span>
* <span data-ttu-id="d1146-106">ServiceSet</span><span class="sxs-lookup"><span data-stu-id="d1146-106">ServiceSet</span></span>
* <span data-ttu-id="d1146-107">ProcessSet</span><span class="sxs-lookup"><span data-stu-id="d1146-107">ProcessSet</span></span>

<span data-ttu-id="d1146-108">Estes recursos fornecem uma maneira fácil de configurar várias instâncias usando uma única chamada de recursos.</span><span class="sxs-lookup"><span data-stu-id="d1146-108">These resources provide an easy way to configure multiple instances using a single resource call.</span></span>

## <a name="windowsfeatureset"></a><span data-ttu-id="d1146-109">WindowsFeatureSet</span><span class="sxs-lookup"><span data-stu-id="d1146-109">WindowsFeatureSet</span></span>

```powershell
# Get the syntax of WindowsFeatureSet resource
Get-DscResource -Module psdesiredstateconfiguration -Name WindowsFeatureSet -Syntax

WindowsFeatureSet [String] #ResourceName
{
    [DependsOn = [String[]]]
    Name = [String[]]
    [Ensure = [String]]
    [Source = [String]]
    [IncludeAllSubFeature = [Boolean]]
    [Credential = [PSCredential]]
    [LogPath = [String]]
}
```

## <a name="windowsoptionalfeatureset"></a><span data-ttu-id="d1146-110">WindowsOptionalFeatureSet</span><span class="sxs-lookup"><span data-stu-id="d1146-110">WindowsOptionalFeatureSet</span></span>

```powershell
# Get the syntax of WindowsOptionalFeatureSet resource
Get-DscResource -Module psdesiredstateconfiguration -Name WindowsOptionalFeatureSet -Syntax

WindowsOptionalFeatureSet [String] #ResourceName
{
    [DependsOn = [String[]]]
    Name = [String[]]
    Ensure = [String]
    [Source = [String[]]]
    [RemoveFilesOnDisable = [Boolean]]
    [LogPath = [String]]
    [NoWindowsUpdateCheck = [Boolean]]
    [LogLevel = [String]]
}
```

## <a name="serviceset"></a><span data-ttu-id="d1146-111">ServiceSet</span><span class="sxs-lookup"><span data-stu-id="d1146-111">ServiceSet</span></span>

```powershell
# Get the syntax of ServiceSet resource
Get-DscResource -Module psdesiredstateconfiguration -Name ServiceSet -Syntax

ServiceSet [String] #ResourceName
{
    [DependsOn = [String[]]]
    Name = [String[]]
    [StartupType = [String]]
    [BuiltInAccount = [String]]
    [State = [String]]
    [Ensure = [String]]
    [Credential = [PSCredential]]
}
```

## <a name="processset"></a><span data-ttu-id="d1146-112">ProcessSet</span><span class="sxs-lookup"><span data-stu-id="d1146-112">ProcessSet</span></span>

```powershell
# Get the syntax of ProcessSet resource
Get-DscResource -Module psdesiredstateconfiguration -Name ProcessSet -Syntax

ProcessSet [String] #ResourceName
{
    [DependsOn = [String[]]]
    Path = [String[]]
    [Credential = [PSCredential]]
    [Ensure = [String]]
    [StandardOutputPath = [String]]
    [StandardErrorPath = [String]]
    [StandardInputPath = [String]]
    [WorkingDirectory = [String]]
}
```
