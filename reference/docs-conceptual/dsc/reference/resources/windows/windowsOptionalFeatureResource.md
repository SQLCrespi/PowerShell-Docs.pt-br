---
ms.date: 08/28/2020
keywords: DSC,powershell,configuração,instalação
title: Recurso do WindowsOptionalFeature DSC
ms.openlocfilehash: f24173c1a9ed605bac43767a9da2d4dbded78883
ms.sourcegitcommit: 06b6f4012e4eca71d414733cdba23ef75535223c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2020
ms.locfileid: "89093243"
---
# <a name="dsc-windowsoptionalfeature-resource"></a><span data-ttu-id="e6af5-103">Recurso do WindowsOptionalFeature DSC</span><span class="sxs-lookup"><span data-stu-id="e6af5-103">DSC WindowsOptionalFeature Resource</span></span>

> <span data-ttu-id="e6af5-104">Aplica-se a: Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="e6af5-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="e6af5-105">O recurso **WindowsOptionalFeature** na DSC (Configuração de Estado Desejado) do Windows PowerShell oferece um mecanismo para garantir que os recursos opcionais sejam habilitados em um nó de destino.</span><span class="sxs-lookup"><span data-stu-id="e6af5-105">The **WindowsOptionalFeature** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that optional features are enabled on a target node.</span></span>

> [!NOTE]
> <span data-ttu-id="e6af5-106">O **WindowsOptionalFeature** só funciona em computadores cliente do Windows, como o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="e6af5-106">**WindowsOptionalFeature** only works on Windows client machines like Windows 10.</span></span>

## <a name="syntax"></a><span data-ttu-id="e6af5-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e6af5-107">Syntax</span></span>

```Syntax
WindowsOptionalFeature [string] #ResourceName
{
    Name = [string]
    [ NoWindowsUpdateCheck = [bool] ]
    [ RemoveFilesOnDisable = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Enable | Disable }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="e6af5-108">Propriedades</span><span class="sxs-lookup"><span data-stu-id="e6af5-108">Properties</span></span>

|<span data-ttu-id="e6af5-109">Propriedade</span><span class="sxs-lookup"><span data-stu-id="e6af5-109">Property</span></span> |<span data-ttu-id="e6af5-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="e6af5-110">Description</span></span> |
|---|---|
|<span data-ttu-id="e6af5-111">Nome</span><span class="sxs-lookup"><span data-stu-id="e6af5-111">Name</span></span> |<span data-ttu-id="e6af5-112">Indica o nome do recurso que você deseja garantir que esteja habilitado ou desabilitado.</span><span class="sxs-lookup"><span data-stu-id="e6af5-112">Indicates the name of the feature that you want to ensure is enabled or disabled.</span></span> |
|<span data-ttu-id="e6af5-113">NoWindowsUpdateCheck</span><span class="sxs-lookup"><span data-stu-id="e6af5-113">NoWindowsUpdateCheck</span></span> |<span data-ttu-id="e6af5-114">Especifica se o DISM contata o WU (Windows Update) ao procurar os arquivos de origem para habilitar um recurso.</span><span class="sxs-lookup"><span data-stu-id="e6af5-114">Specifies whether DISM contacts Windows Update (WU) when searching for the source files to enable a feature.</span></span> <span data-ttu-id="e6af5-115">Se `$true`, o DISM não contatará o WU.</span><span class="sxs-lookup"><span data-stu-id="e6af5-115">If `$true`, DISM does not contact WU.</span></span> |
|<span data-ttu-id="e6af5-116">RemoveFilesOnDisable</span><span class="sxs-lookup"><span data-stu-id="e6af5-116">RemoveFilesOnDisable</span></span> |<span data-ttu-id="e6af5-117">Definido como `$true` para remover todos os arquivos associados ao recurso quando **Ensure** estiver definido como **Absent**.</span><span class="sxs-lookup"><span data-stu-id="e6af5-117">Set to `$true` to remove all files associated with the feature when **Ensure** is set to **Absent**.</span></span> |
|<span data-ttu-id="e6af5-118">LogLevel</span><span class="sxs-lookup"><span data-stu-id="e6af5-118">LogLevel</span></span> |<span data-ttu-id="e6af5-119">O nível máximo de saída mostrado nos logs.</span><span class="sxs-lookup"><span data-stu-id="e6af5-119">The maximum output level shown in the logs.</span></span> <span data-ttu-id="e6af5-120">Os valores aceitos são: **ErrorsOnly**, **ErrorsAndWarning** e **ErrorsAndWarningAndInformation**.</span><span class="sxs-lookup"><span data-stu-id="e6af5-120">The accepted values are: **ErrorsOnly**, **ErrorsAndWarning**, and **ErrorsAndWarningAndInformation**.</span></span> |
|<span data-ttu-id="e6af5-121">LogPath</span><span class="sxs-lookup"><span data-stu-id="e6af5-121">LogPath</span></span> |<span data-ttu-id="e6af5-122">O caminho até um arquivo de log em que você deseja que o provedor de recursos registre a operação.</span><span class="sxs-lookup"><span data-stu-id="e6af5-122">The path to a log file where you want the resource provider to log the operation.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="e6af5-123">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="e6af5-123">Common properties</span></span>

|<span data-ttu-id="e6af5-124">Propriedade</span><span class="sxs-lookup"><span data-stu-id="e6af5-124">Property</span></span> |<span data-ttu-id="e6af5-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="e6af5-125">Description</span></span> |
|---|---|
|<span data-ttu-id="e6af5-126">DependsOn</span><span class="sxs-lookup"><span data-stu-id="e6af5-126">DependsOn</span></span> |<span data-ttu-id="e6af5-127">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="e6af5-127">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="e6af5-128">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="e6af5-128">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="e6af5-129">Ensure</span><span class="sxs-lookup"><span data-stu-id="e6af5-129">Ensure</span></span> |<span data-ttu-id="e6af5-130">Especifica se o recurso está habilitado.</span><span class="sxs-lookup"><span data-stu-id="e6af5-130">Specifies whether the feature is enabled.</span></span> <span data-ttu-id="e6af5-131">Para garantir que o recurso seja habilitado, defina essa propriedade como _Enable_.</span><span class="sxs-lookup"><span data-stu-id="e6af5-131">To ensure that the feature is enabled, set this property to _Enable_.</span></span> <span data-ttu-id="e6af5-132">Para garantir que o recurso seja desabilitado, defina essa propriedade como _Disable_.</span><span class="sxs-lookup"><span data-stu-id="e6af5-132">To ensure that the feature is disabled, set the property to _Disable_.</span></span> <span data-ttu-id="e6af5-133">O valor padrão é _Enable_.</span><span class="sxs-lookup"><span data-stu-id="e6af5-133">The default value is _Enable_.</span></span> |
|<span data-ttu-id="e6af5-134">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="e6af5-134">PsDscRunAsCredential</span></span> |<span data-ttu-id="e6af5-135">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="e6af5-135">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="e6af5-136">A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais.</span><span class="sxs-lookup"><span data-stu-id="e6af5-136">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="e6af5-137">Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="e6af5-137">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>
