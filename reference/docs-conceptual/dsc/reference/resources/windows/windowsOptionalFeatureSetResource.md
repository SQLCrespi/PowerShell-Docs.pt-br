---
ms.date: 07/16/2020
ms.topic: reference
title: Recurso do WindowsOptionalFeatureSet DSC
description: Recurso do WindowsOptionalFeatureSet DSC
ms.openlocfilehash: f72cc27bfc8847d2c87cfb289f3e2c729a21d1f4
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2020
ms.locfileid: "93143034"
---
# <a name="dsc-windowsoptionalfeatureset-resource"></a><span data-ttu-id="0c53e-103">Recurso do WindowsOptionalFeatureSet DSC</span><span class="sxs-lookup"><span data-stu-id="0c53e-103">DSC WindowsOptionalFeatureSet Resource</span></span>

> <span data-ttu-id="0c53e-104">Aplica-se a: Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="0c53e-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="0c53e-105">O recurso **WindowsOptionalFeatureSet** na DSC (Configuração de Estado Desejado) do Windows PowerShell oferece um mecanismo para garantir que os recursos opcionais sejam habilitados em um nó de destino.</span><span class="sxs-lookup"><span data-stu-id="0c53e-105">The **WindowsOptionalFeatureSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that optional features are enabled on a target node.</span></span> <span data-ttu-id="0c53e-106">Esse recurso é um [recurso composto](../../../resources/authoringResourceComposite.md) que chama o [recurso WindowsOptionalFeature](windowsOptionalFeatureResource.md) para cada recurso especificado na propriedade **Name** .</span><span class="sxs-lookup"><span data-stu-id="0c53e-106">This resource is a [composite resource](../../../resources/authoringResourceComposite.md) that calls the [WindowsOptionalFeature resource](windowsOptionalFeatureResource.md) for each feature specified in the **Name** property.</span></span>

<span data-ttu-id="0c53e-107">Use esse recurso quando desejar configurar vários recursos opcionais do Windows para o mesmo estado.</span><span class="sxs-lookup"><span data-stu-id="0c53e-107">Use this resource when you want to configure a number of Windows optional features to the same state.</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a><span data-ttu-id="0c53e-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0c53e-108">Syntax</span></span>

```Syntax
WindowsOptionalFeatureSet [string] #ResourceName
{
    Name = [string[]]
    [ RemoveFilesOnDisable = [bool] ]
    [ LogPath = [string] ]
    [ NoWindowsUpdateCheck = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Enable | Disable }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="0c53e-109">Propriedades</span><span class="sxs-lookup"><span data-stu-id="0c53e-109">Properties</span></span>

|<span data-ttu-id="0c53e-110">Propriedade</span><span class="sxs-lookup"><span data-stu-id="0c53e-110">Property</span></span> |<span data-ttu-id="0c53e-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="0c53e-111">Description</span></span> |
|---|---|
|<span data-ttu-id="0c53e-112">Nome</span><span class="sxs-lookup"><span data-stu-id="0c53e-112">Name</span></span> |<span data-ttu-id="0c53e-113">Indica o nome dos recursos que você deseja garantir que estejam habilitados ou desabilitados.</span><span class="sxs-lookup"><span data-stu-id="0c53e-113">Indicates the name of the features that you want to ensure are enabled or disabled.</span></span> |
|<span data-ttu-id="0c53e-114">NoWindowsUpdateCheck</span><span class="sxs-lookup"><span data-stu-id="0c53e-114">NoWindowsUpdateCheck</span></span> |<span data-ttu-id="0c53e-115">Especifica se o DISM contata o WU (Windows Update) ao procurar os arquivos de origem para habilitar recursos.</span><span class="sxs-lookup"><span data-stu-id="0c53e-115">Specifies whether DISM contacts Windows Update (WU) when searching for the source files to enable features.</span></span> <span data-ttu-id="0c53e-116">Se `$true`, o DISM não contatará o WU.</span><span class="sxs-lookup"><span data-stu-id="0c53e-116">If `$true`, DISM does not contact WU.</span></span> |
|<span data-ttu-id="0c53e-117">RemoveFilesOnDisable</span><span class="sxs-lookup"><span data-stu-id="0c53e-117">RemoveFilesOnDisable</span></span> |<span data-ttu-id="0c53e-118">Definido como `$true` para remover todos os arquivos associados aos recursos quando **Ensure** está definido como **Absent** .</span><span class="sxs-lookup"><span data-stu-id="0c53e-118">Set to `$true` to remove all files associated with the features when **Ensure** is set to **Absent** .</span></span> |
|<span data-ttu-id="0c53e-119">LogLevel</span><span class="sxs-lookup"><span data-stu-id="0c53e-119">LogLevel</span></span> |<span data-ttu-id="0c53e-120">O nível máximo de saída mostrado nos logs.</span><span class="sxs-lookup"><span data-stu-id="0c53e-120">The maximum output level shown in the logs.</span></span> <span data-ttu-id="0c53e-121">Os valores aceitos são: **ErrorsOnly** , **ErrorsAndWarning** e **ErrorsAndWarningAndInformation** .</span><span class="sxs-lookup"><span data-stu-id="0c53e-121">The accepted values are: **ErrorsOnly** , **ErrorsAndWarning** , and **ErrorsAndWarningAndInformation** .</span></span> |
|<span data-ttu-id="0c53e-122">LogPath</span><span class="sxs-lookup"><span data-stu-id="0c53e-122">LogPath</span></span> |<span data-ttu-id="0c53e-123">O caminho até um arquivo de log em que você deseja que o provedor de recursos registre a operação.</span><span class="sxs-lookup"><span data-stu-id="0c53e-123">The path to a log file where you want the resource provider to log the operation.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="0c53e-124">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="0c53e-124">Common properties</span></span>

|<span data-ttu-id="0c53e-125">Propriedade</span><span class="sxs-lookup"><span data-stu-id="0c53e-125">Property</span></span> |<span data-ttu-id="0c53e-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="0c53e-126">Description</span></span> |
|---|---|
|<span data-ttu-id="0c53e-127">DependsOn</span><span class="sxs-lookup"><span data-stu-id="0c53e-127">DependsOn</span></span> |<span data-ttu-id="0c53e-128">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="0c53e-128">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="0c53e-129">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="0c53e-129">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="0c53e-130">Ensure</span><span class="sxs-lookup"><span data-stu-id="0c53e-130">Ensure</span></span> |<span data-ttu-id="0c53e-131">Especifica se os recursos estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="0c53e-131">Specifies whether the features are enabled.</span></span> <span data-ttu-id="0c53e-132">Para garantir que os recursos sejam habilitados, defina essa propriedade como **Enable** .</span><span class="sxs-lookup"><span data-stu-id="0c53e-132">To ensure that the features are enabled, set this property to **Enable** .</span></span> <span data-ttu-id="0c53e-133">Para garantir que os recursos sejam desabilitados, defina essa propriedade como **Disable** .</span><span class="sxs-lookup"><span data-stu-id="0c53e-133">To ensure that the features are disabled, set the property to **Disable** .</span></span> <span data-ttu-id="0c53e-134">O valor padrão é **Enable** .</span><span class="sxs-lookup"><span data-stu-id="0c53e-134">The default value is **Enable** .</span></span> |
|<span data-ttu-id="0c53e-135">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="0c53e-135">PsDscRunAsCredential</span></span> |<span data-ttu-id="0c53e-136">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="0c53e-136">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="0c53e-137">A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais.</span><span class="sxs-lookup"><span data-stu-id="0c53e-137">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="0c53e-138">Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="0c53e-138">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>
