---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso do WindowsOptionalFeature DSC
ms.openlocfilehash: bca6294db74c92a2c1940cfbe00305542a1c5d19
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83565359"
---
# <a name="dsc-windowsoptionalfeature-resource"></a><span data-ttu-id="1132a-103">Recurso do WindowsOptionalFeature DSC</span><span class="sxs-lookup"><span data-stu-id="1132a-103">DSC WindowsOptionalFeature Resource</span></span>

> <span data-ttu-id="1132a-104">Aplica-se a: Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="1132a-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="1132a-105">O recurso **WindowsOptionalFeature** na DSC (Configuração de Estado Desejado) do Windows PowerShell oferece um mecanismo para garantir que os recursos opcionais sejam habilitados em um nó de destino.</span><span class="sxs-lookup"><span data-stu-id="1132a-105">The **WindowsOptionalFeature** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that optional features are enabled on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="1132a-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1132a-106">Syntax</span></span>

```Syntax
WindowsOptionalFeature [string] #ResourceName
{
    Name = [string]
    [ Source = [string[]] ]
    [ NoWindowsUpdateCheck = [bool] ]
    [ RemoveFilesOnDisable = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Enable | Disable }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="1132a-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="1132a-107">Properties</span></span>

|<span data-ttu-id="1132a-108">Propriedade</span><span class="sxs-lookup"><span data-stu-id="1132a-108">Property</span></span> |<span data-ttu-id="1132a-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="1132a-109">Description</span></span> |
|---|---|
|<span data-ttu-id="1132a-110">Nome</span><span class="sxs-lookup"><span data-stu-id="1132a-110">Name</span></span> |<span data-ttu-id="1132a-111">Indica o nome do recurso que você deseja garantir que esteja habilitado ou desabilitado.</span><span class="sxs-lookup"><span data-stu-id="1132a-111">Indicates the name of the feature that you want to ensure is enabled or disabled.</span></span> |
|<span data-ttu-id="1132a-112">Fonte</span><span class="sxs-lookup"><span data-stu-id="1132a-112">Source</span></span> |<span data-ttu-id="1132a-113">Não implementado.</span><span class="sxs-lookup"><span data-stu-id="1132a-113">Not implemented.</span></span> |
|<span data-ttu-id="1132a-114">NoWindowsUpdateCheck</span><span class="sxs-lookup"><span data-stu-id="1132a-114">NoWindowsUpdateCheck</span></span> |<span data-ttu-id="1132a-115">Especifica se o DISM contata o WU (Windows Update) ao procurar os arquivos de origem para habilitar um recurso.</span><span class="sxs-lookup"><span data-stu-id="1132a-115">Specifies whether DISM contacts Windows Update (WU) when searching for the source files to enable a feature.</span></span> <span data-ttu-id="1132a-116">Se `$true`, o DISM não contatará o WU.</span><span class="sxs-lookup"><span data-stu-id="1132a-116">If `$true`, DISM does not contact WU.</span></span> |
|<span data-ttu-id="1132a-117">RemoveFilesOnDisable</span><span class="sxs-lookup"><span data-stu-id="1132a-117">RemoveFilesOnDisable</span></span> |<span data-ttu-id="1132a-118">Definido como `$true` para remover todos os arquivos associados ao recurso quando **Ensure** estiver definido como **Absent**.</span><span class="sxs-lookup"><span data-stu-id="1132a-118">Set to `$true` to remove all files associated with the feature when **Ensure** is set to **Absent**.</span></span> |
|<span data-ttu-id="1132a-119">LogLevel</span><span class="sxs-lookup"><span data-stu-id="1132a-119">LogLevel</span></span> |<span data-ttu-id="1132a-120">O nível máximo de saída mostrado nos logs.</span><span class="sxs-lookup"><span data-stu-id="1132a-120">The maximum output level shown in the logs.</span></span> <span data-ttu-id="1132a-121">Os valores aceitos são: **ErrorsOnly**, **ErrorsAndWarning** e **ErrorsAndWarningAndInformation**.</span><span class="sxs-lookup"><span data-stu-id="1132a-121">The accepted values are: **ErrorsOnly**, **ErrorsAndWarning**, and **ErrorsAndWarningAndInformation**.</span></span> |
|<span data-ttu-id="1132a-122">LogPath</span><span class="sxs-lookup"><span data-stu-id="1132a-122">LogPath</span></span> |<span data-ttu-id="1132a-123">O caminho até um arquivo de log em que você deseja que o provedor de recursos registre a operação.</span><span class="sxs-lookup"><span data-stu-id="1132a-123">The path to a log file where you want the resource provider to log the operation.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="1132a-124">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="1132a-124">Common properties</span></span>

|<span data-ttu-id="1132a-125">Propriedade</span><span class="sxs-lookup"><span data-stu-id="1132a-125">Property</span></span> |<span data-ttu-id="1132a-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="1132a-126">Description</span></span> |
|---|---|
|<span data-ttu-id="1132a-127">DependsOn</span><span class="sxs-lookup"><span data-stu-id="1132a-127">DependsOn</span></span> |<span data-ttu-id="1132a-128">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="1132a-128">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="1132a-129">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="1132a-129">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="1132a-130">Ensure</span><span class="sxs-lookup"><span data-stu-id="1132a-130">Ensure</span></span> |<span data-ttu-id="1132a-131">Especifica se o recurso está habilitado.</span><span class="sxs-lookup"><span data-stu-id="1132a-131">Specifies whether the feature is enabled.</span></span> <span data-ttu-id="1132a-132">Para garantir que o recurso seja habilitado, defina essa propriedade como _Enable_.</span><span class="sxs-lookup"><span data-stu-id="1132a-132">To ensure that the feature is enabled, set this property to _Enable_.</span></span> <span data-ttu-id="1132a-133">Para garantir que o recurso seja desabilitado, defina essa propriedade como _Disable_.</span><span class="sxs-lookup"><span data-stu-id="1132a-133">To ensure that the feature is disabled, set the property to _Disable_.</span></span> <span data-ttu-id="1132a-134">O valor padrão é _Enable_.</span><span class="sxs-lookup"><span data-stu-id="1132a-134">The default value is _Enable_.</span></span> |
|<span data-ttu-id="1132a-135">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="1132a-135">PsDscRunAsCredential</span></span> |<span data-ttu-id="1132a-136">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="1132a-136">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="1132a-137">A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais.</span><span class="sxs-lookup"><span data-stu-id="1132a-137">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="1132a-138">Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="1132a-138">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>
