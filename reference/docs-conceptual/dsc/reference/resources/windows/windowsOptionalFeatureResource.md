---
ms.date: 08/28/2020
ms.topic: reference
title: Recurso do WindowsOptionalFeature DSC
description: Recurso do WindowsOptionalFeature DSC
ms.openlocfilehash: 1c7e888ea49b0d1710cc22c975cb618999238f67
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2020
ms.locfileid: "93143051"
---
# <a name="dsc-windowsoptionalfeature-resource"></a><span data-ttu-id="0ec97-103">Recurso do WindowsOptionalFeature DSC</span><span class="sxs-lookup"><span data-stu-id="0ec97-103">DSC WindowsOptionalFeature Resource</span></span>

> <span data-ttu-id="0ec97-104">Aplica-se a: Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="0ec97-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="0ec97-105">O recurso **WindowsOptionalFeature** na DSC (Configuração de Estado Desejado) do Windows PowerShell oferece um mecanismo para garantir que os recursos opcionais sejam habilitados em um nó de destino.</span><span class="sxs-lookup"><span data-stu-id="0ec97-105">The **WindowsOptionalFeature** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that optional features are enabled on a target node.</span></span>

> [!NOTE]
> <span data-ttu-id="0ec97-106">O **WindowsOptionalFeature** só funciona em computadores cliente do Windows, como o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="0ec97-106">**WindowsOptionalFeature** only works on Windows client machines like Windows 10.</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a><span data-ttu-id="0ec97-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0ec97-107">Syntax</span></span>

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

## <a name="properties"></a><span data-ttu-id="0ec97-108">Propriedades</span><span class="sxs-lookup"><span data-stu-id="0ec97-108">Properties</span></span>

|<span data-ttu-id="0ec97-109">Propriedade</span><span class="sxs-lookup"><span data-stu-id="0ec97-109">Property</span></span> |<span data-ttu-id="0ec97-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="0ec97-110">Description</span></span> |
|---|---|
|<span data-ttu-id="0ec97-111">Nome</span><span class="sxs-lookup"><span data-stu-id="0ec97-111">Name</span></span> |<span data-ttu-id="0ec97-112">Indica o nome do recurso que você deseja garantir que esteja habilitado ou desabilitado.</span><span class="sxs-lookup"><span data-stu-id="0ec97-112">Indicates the name of the feature that you want to ensure is enabled or disabled.</span></span> |
|<span data-ttu-id="0ec97-113">NoWindowsUpdateCheck</span><span class="sxs-lookup"><span data-stu-id="0ec97-113">NoWindowsUpdateCheck</span></span> |<span data-ttu-id="0ec97-114">Especifica se o DISM contata o WU (Windows Update) ao procurar os arquivos de origem para habilitar um recurso.</span><span class="sxs-lookup"><span data-stu-id="0ec97-114">Specifies whether DISM contacts Windows Update (WU) when searching for the source files to enable a feature.</span></span> <span data-ttu-id="0ec97-115">Se `$true`, o DISM não contatará o WU.</span><span class="sxs-lookup"><span data-stu-id="0ec97-115">If `$true`, DISM does not contact WU.</span></span> |
|<span data-ttu-id="0ec97-116">RemoveFilesOnDisable</span><span class="sxs-lookup"><span data-stu-id="0ec97-116">RemoveFilesOnDisable</span></span> |<span data-ttu-id="0ec97-117">Definido como `$true` para remover todos os arquivos associados ao recurso quando **Ensure** estiver definido como **Absent** .</span><span class="sxs-lookup"><span data-stu-id="0ec97-117">Set to `$true` to remove all files associated with the feature when **Ensure** is set to **Absent** .</span></span> |
|<span data-ttu-id="0ec97-118">LogLevel</span><span class="sxs-lookup"><span data-stu-id="0ec97-118">LogLevel</span></span> |<span data-ttu-id="0ec97-119">O nível máximo de saída mostrado nos logs.</span><span class="sxs-lookup"><span data-stu-id="0ec97-119">The maximum output level shown in the logs.</span></span> <span data-ttu-id="0ec97-120">Os valores aceitos são: **ErrorsOnly** , **ErrorsAndWarning** e **ErrorsAndWarningAndInformation** .</span><span class="sxs-lookup"><span data-stu-id="0ec97-120">The accepted values are: **ErrorsOnly** , **ErrorsAndWarning** , and **ErrorsAndWarningAndInformation** .</span></span> |
|<span data-ttu-id="0ec97-121">LogPath</span><span class="sxs-lookup"><span data-stu-id="0ec97-121">LogPath</span></span> |<span data-ttu-id="0ec97-122">O caminho até um arquivo de log em que você deseja que o provedor de recursos registre a operação.</span><span class="sxs-lookup"><span data-stu-id="0ec97-122">The path to a log file where you want the resource provider to log the operation.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="0ec97-123">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="0ec97-123">Common properties</span></span>

|<span data-ttu-id="0ec97-124">Propriedade</span><span class="sxs-lookup"><span data-stu-id="0ec97-124">Property</span></span> |<span data-ttu-id="0ec97-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="0ec97-125">Description</span></span> |
|---|---|
|<span data-ttu-id="0ec97-126">DependsOn</span><span class="sxs-lookup"><span data-stu-id="0ec97-126">DependsOn</span></span> |<span data-ttu-id="0ec97-127">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="0ec97-127">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="0ec97-128">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="0ec97-128">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="0ec97-129">Ensure</span><span class="sxs-lookup"><span data-stu-id="0ec97-129">Ensure</span></span> |<span data-ttu-id="0ec97-130">Especifica se o recurso está habilitado.</span><span class="sxs-lookup"><span data-stu-id="0ec97-130">Specifies whether the feature is enabled.</span></span> <span data-ttu-id="0ec97-131">Para garantir que o recurso seja habilitado, defina essa propriedade como _Enable_ .</span><span class="sxs-lookup"><span data-stu-id="0ec97-131">To ensure that the feature is enabled, set this property to _Enable_ .</span></span> <span data-ttu-id="0ec97-132">Para garantir que o recurso seja desabilitado, defina essa propriedade como _Disable_ .</span><span class="sxs-lookup"><span data-stu-id="0ec97-132">To ensure that the feature is disabled, set the property to _Disable_ .</span></span> <span data-ttu-id="0ec97-133">O valor padrão é _Enable_ .</span><span class="sxs-lookup"><span data-stu-id="0ec97-133">The default value is _Enable_ .</span></span> |
|<span data-ttu-id="0ec97-134">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="0ec97-134">PsDscRunAsCredential</span></span> |<span data-ttu-id="0ec97-135">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="0ec97-135">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="0ec97-136">A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais.</span><span class="sxs-lookup"><span data-stu-id="0ec97-136">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="0ec97-137">Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="0ec97-137">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>
