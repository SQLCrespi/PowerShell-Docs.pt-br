---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso do WindowsFeatureSet DSC
ms.openlocfilehash: 1758d248dde4fdee57bd01c157a3f9a8340d6194
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "71952953"
---
# <a name="dsc-windowsfeatureset-resource"></a><span data-ttu-id="5099e-103">Recurso do WindowsFeatureSet DSC</span><span class="sxs-lookup"><span data-stu-id="5099e-103">DSC WindowsFeatureSet Resource</span></span>

> <span data-ttu-id="5099e-104">Aplica-se a: Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="5099e-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="5099e-105">O recurso **WindowsFeatureSet** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para garantir que funções e recursos sejam adicionados ou removidos em um nó de destino.</span><span class="sxs-lookup"><span data-stu-id="5099e-105">The **WindowsFeatureSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that roles and features are added or removed on a target node.</span></span> <span data-ttu-id="5099e-106">Esse recurso é um [recurso composto](../../../resources/authoringResourceComposite.md) que chama o [recurso WindowsFeature](windowsfeatureResource.md) para cada recurso especificado na propriedade **Name**.</span><span class="sxs-lookup"><span data-stu-id="5099e-106">This resource is a [composite resource](../../../resources/authoringResourceComposite.md) that calls the [WindowsFeature resource](windowsfeatureResource.md) for each feature specified in the **Name** property.</span></span>

<span data-ttu-id="5099e-107">Use esse recurso quando desejar configurar vários Recursos do Windows para o mesmo estado.</span><span class="sxs-lookup"><span data-stu-id="5099e-107">Use this resource when you want to configure a number of Windows Features to the same state.</span></span>

## <a name="syntax"></a><span data-ttu-id="5099e-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5099e-108">Syntax</span></span>

```Syntax
WindowsFeatureSet [string] #ResourceName
{
    Name = [string[]]
    [ Source = [string] ]
    [ IncludeAllSubFeature = [Boolean] ]
    [ Credential = [PSCredential] ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="5099e-109">Propriedades</span><span class="sxs-lookup"><span data-stu-id="5099e-109">Properties</span></span>

|  <span data-ttu-id="5099e-110">Propriedade</span><span class="sxs-lookup"><span data-stu-id="5099e-110">Property</span></span>  |  <span data-ttu-id="5099e-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="5099e-111">Description</span></span>   |
|---|---|
|<span data-ttu-id="5099e-112">Nome</span><span class="sxs-lookup"><span data-stu-id="5099e-112">Name</span></span> |<span data-ttu-id="5099e-113">Os nomes de funções ou recursos que você deseja garantir são adicionados ou removidos.</span><span class="sxs-lookup"><span data-stu-id="5099e-113">The names of the roles or features that you want to ensure are added or removed.</span></span> <span data-ttu-id="5099e-114">É igual à propriedade **Name** do cmdlet [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature?view=winserver2012r2-ps), e não o nome de exibição das funções ou recursos.</span><span class="sxs-lookup"><span data-stu-id="5099e-114">This is the same as the **Name** property of the [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature?view=winserver2012r2-ps) cmdlet, and not the display name of the roles or features.</span></span> |
|<span data-ttu-id="5099e-115">Origem</span><span class="sxs-lookup"><span data-stu-id="5099e-115">Source</span></span> |<span data-ttu-id="5099e-116">Indica o local do arquivo de origem que deve ser usado para a instalação, se necessário.</span><span class="sxs-lookup"><span data-stu-id="5099e-116">Indicates the location of the source file to use for installation, if necessary.</span></span> |
|<span data-ttu-id="5099e-117">IncludeAllSubFeature</span><span class="sxs-lookup"><span data-stu-id="5099e-117">IncludeAllSubFeature</span></span> |<span data-ttu-id="5099e-118">Defina essa propriedade como `$true` para incluir todos os sub-recursos com os recursos especificados com a propriedade **Name**.</span><span class="sxs-lookup"><span data-stu-id="5099e-118">Set this property to `$true` to include all required subfeatures with of the features you specify with the **Name** property.</span></span> |
|<span data-ttu-id="5099e-119">Credential</span><span class="sxs-lookup"><span data-stu-id="5099e-119">Credential</span></span> |<span data-ttu-id="5099e-120">As credenciais que devem ser usadas para adicionar ou remover as funções ou os recursos.</span><span class="sxs-lookup"><span data-stu-id="5099e-120">The credentials to use to add or remove the roles or features.</span></span> |
|<span data-ttu-id="5099e-121">LogPath</span><span class="sxs-lookup"><span data-stu-id="5099e-121">LogPath</span></span> |<span data-ttu-id="5099e-122">O caminho até um arquivo de log em que você deseja que o provedor de recursos registre a operação.</span><span class="sxs-lookup"><span data-stu-id="5099e-122">The path to a log file where you want the resource provider to log the operation.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="5099e-123">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="5099e-123">Common properties</span></span>

|<span data-ttu-id="5099e-124">Propriedade</span><span class="sxs-lookup"><span data-stu-id="5099e-124">Property</span></span> |<span data-ttu-id="5099e-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="5099e-125">Description</span></span> |
|---|---|
|<span data-ttu-id="5099e-126">DependsOn</span><span class="sxs-lookup"><span data-stu-id="5099e-126">DependsOn</span></span> |<span data-ttu-id="5099e-127">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="5099e-127">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="5099e-128">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="5099e-128">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="5099e-129">Ensure</span><span class="sxs-lookup"><span data-stu-id="5099e-129">Ensure</span></span> |<span data-ttu-id="5099e-130">Indica se as funções ou os recursos são adicionados.</span><span class="sxs-lookup"><span data-stu-id="5099e-130">Indicates whether the roles or features are added.</span></span> <span data-ttu-id="5099e-131">Para garantir que as funções e os recursos sejam adicionados, defina essa propriedade como **Present**.</span><span class="sxs-lookup"><span data-stu-id="5099e-131">To ensure that the roles or features are added, set this property to **Present**.</span></span> <span data-ttu-id="5099e-132">Para garantir que as funções e os recursos sejam removidos, defina essa propriedade como **Absent**.</span><span class="sxs-lookup"><span data-stu-id="5099e-132">To ensure that the roles or features are removed, set the property to **Absent**.</span></span> <span data-ttu-id="5099e-133">O valor padrão é **Present**.</span><span class="sxs-lookup"><span data-stu-id="5099e-133">The default value is **Present**.</span></span> |
|<span data-ttu-id="5099e-134">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="5099e-134">PsDscRunAsCredential</span></span> |<span data-ttu-id="5099e-135">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="5099e-135">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="5099e-136">A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais.</span><span class="sxs-lookup"><span data-stu-id="5099e-136">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="5099e-137">Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="5099e-137">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="5099e-138">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5099e-138">Example</span></span>

<span data-ttu-id="5099e-139">A configuração a seguir garante que os recursos **Servidor Web** (IIS) e **Servidor SMTP** e todos os sub-recursos de cada um sejam instalados.</span><span class="sxs-lookup"><span data-stu-id="5099e-139">The following configuration ensures that the **Web-Server** (IIS) and **SMTP Server** features, and all subfeatures of each, are installed.</span></span>

```powershell
configuration FeatureSetTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {

        WindowsFeatureSet WindowsFeatureSetExample
        {
            Name                    = @("SMTP-Server", "Web-Server")
            Ensure                  = 'Present'
            IncludeAllSubFeature    = $true
        }
    }
}
```