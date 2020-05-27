---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso WindowsFeature de DSC
ms.openlocfilehash: 7f9b200b4d10aef6c8a3f76c497f4d60e8062cb5
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83557390"
---
# <a name="dsc-windowsfeature-resource"></a><span data-ttu-id="e12d1-103">Recurso WindowsFeature de DSC</span><span class="sxs-lookup"><span data-stu-id="e12d1-103">DSC WindowsFeature Resource</span></span>

> <span data-ttu-id="e12d1-104">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="e12d1-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="e12d1-105">O recurso **WindowsFeature** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para garantir que funções e recursos sejam adicionados ou removidos em um nó de destino.</span><span class="sxs-lookup"><span data-stu-id="e12d1-105">The **WindowsFeature** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that roles and features are added or removed on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="e12d1-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e12d1-106">Syntax</span></span>

```Syntax
WindowsFeature [string] #ResourceName
{
    Name = [string]
    [ Credential = [PSCredential] ]
    [ IncludeAllSubFeature = [bool] ]
    [ LogPath = [string] ]
    [ Source = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="e12d1-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="e12d1-107">Properties</span></span>

|<span data-ttu-id="e12d1-108">Propriedade</span><span class="sxs-lookup"><span data-stu-id="e12d1-108">Property</span></span> |<span data-ttu-id="e12d1-109">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="e12d1-109">Description</span></span> |
|---|---|
|<span data-ttu-id="e12d1-110">Nome</span><span class="sxs-lookup"><span data-stu-id="e12d1-110">Name</span></span> |<span data-ttu-id="e12d1-111">Indica o nome da função ou recurso que você deseja garantir que seja adicionado ou removido.</span><span class="sxs-lookup"><span data-stu-id="e12d1-111">Indicates the name of the role or feature that you want to ensure is added or removed.</span></span> <span data-ttu-id="e12d1-112">É igual à propriedade **Name** do cmdlet [Get-WindowsFeature](/powershell/module/servermanager/Get-WindowsFeature), não o nome de exibição da função ou recurso.</span><span class="sxs-lookup"><span data-stu-id="e12d1-112">This is the same as the **Name** property from the [Get-WindowsFeature](/powershell/module/servermanager/Get-WindowsFeature) cmdlet, and not the display name of the role or feature.</span></span> |
|<span data-ttu-id="e12d1-113">Credencial</span><span class="sxs-lookup"><span data-stu-id="e12d1-113">Credential</span></span> |<span data-ttu-id="e12d1-114">Indica as credenciais que devem ser usadas para adicionar ou remover a função ou recurso.</span><span class="sxs-lookup"><span data-stu-id="e12d1-114">Indicates the credentials to use to add or remove the role or feature.</span></span> |
|<span data-ttu-id="e12d1-115">IncludeAllSubFeature</span><span class="sxs-lookup"><span data-stu-id="e12d1-115">IncludeAllSubFeature</span></span> |<span data-ttu-id="e12d1-116">Defina essa propriedade como `$true` para garantir o estado de todos os sub-recursos necessários com o estado do recurso especificado com a propriedade **Name**.</span><span class="sxs-lookup"><span data-stu-id="e12d1-116">Set this property to `$true` to ensure the state of all required subfeatures with the state of the feature you specify with the **Name** property.</span></span> |
|<span data-ttu-id="e12d1-117">LogPath</span><span class="sxs-lookup"><span data-stu-id="e12d1-117">LogPath</span></span> |<span data-ttu-id="e12d1-118">Indica o caminho até um arquivo de log em que você deseja que o provedor de recursos registre a operação.</span><span class="sxs-lookup"><span data-stu-id="e12d1-118">Indicates the path to a log file where you want the resource provider to log the operation.</span></span> |
|<span data-ttu-id="e12d1-119">Fonte</span><span class="sxs-lookup"><span data-stu-id="e12d1-119">Source</span></span> |<span data-ttu-id="e12d1-120">Indica o local do arquivo de origem que deve ser usado para a instalação, se necessário.</span><span class="sxs-lookup"><span data-stu-id="e12d1-120">Indicates the location of the source file to use for installation, if necessary.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="e12d1-121">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="e12d1-121">Common properties</span></span>

|<span data-ttu-id="e12d1-122">Propriedade</span><span class="sxs-lookup"><span data-stu-id="e12d1-122">Property</span></span> |<span data-ttu-id="e12d1-123">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="e12d1-123">Description</span></span> |
|---|---|
|<span data-ttu-id="e12d1-124">DependsOn</span><span class="sxs-lookup"><span data-stu-id="e12d1-124">DependsOn</span></span> |<span data-ttu-id="e12d1-125">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="e12d1-125">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="e12d1-126">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="e12d1-126">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="e12d1-127">Ensure</span><span class="sxs-lookup"><span data-stu-id="e12d1-127">Ensure</span></span> |<span data-ttu-id="e12d1-128">Indica se a função ou o recurso foi adicionado.</span><span class="sxs-lookup"><span data-stu-id="e12d1-128">Indicates if the role or feature is added.</span></span> <span data-ttu-id="e12d1-129">Para garantir que a função ou o recurso sejam adicionados, defina essa propriedade como **Present**.</span><span class="sxs-lookup"><span data-stu-id="e12d1-129">To ensure that the role or feature is added, set this property to **Present**.</span></span> <span data-ttu-id="e12d1-130">Para garantir que a função ou o recurso sejam removidos, defina essa propriedade como **Absent**.</span><span class="sxs-lookup"><span data-stu-id="e12d1-130">To ensure that the role or feature is removed, set the property to **Absent**.</span></span> <span data-ttu-id="e12d1-131">O valor padrão é **Present**.</span><span class="sxs-lookup"><span data-stu-id="e12d1-131">The default value is **Present**.</span></span> |
|<span data-ttu-id="e12d1-132">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="e12d1-132">PsDscRunAsCredential</span></span> |<span data-ttu-id="e12d1-133">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="e12d1-133">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="e12d1-134">A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais.</span><span class="sxs-lookup"><span data-stu-id="e12d1-134">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="e12d1-135">Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="e12d1-135">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="e12d1-136">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e12d1-136">Example</span></span>

```powershell
WindowsFeature RoleExample
{
    Ensure = "Present"
    # Alternatively, to ensure the role is uninstalled, set Ensure to "Absent"
    Name = "Web-Server" # Use the Name property from Get-WindowsFeature
}
```
