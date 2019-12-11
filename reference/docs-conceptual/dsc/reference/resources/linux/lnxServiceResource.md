---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso nxService de DSC para Linux
ms.openlocfilehash: 6bb58796c4deff1153f932f61c328d84f8c4d2ca
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "71954833"
---
# <a name="dsc-for-linux-nxservice-resource"></a><span data-ttu-id="8f269-103">Recurso nxService de DSC para Linux</span><span class="sxs-lookup"><span data-stu-id="8f269-103">DSC for Linux nxService Resource</span></span>

<span data-ttu-id="8f269-104">O recurso **nxService** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para gerenciar serviços em um nó do Linux.</span><span class="sxs-lookup"><span data-stu-id="8f269-104">The **nxService** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage services on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="8f269-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8f269-105">Syntax</span></span>

```Syntax
nxService <string> #ResourceName
{
    Name = <string>
    [ Controller = <string> { init | upstart | systemd } ]
    [ Enabled = <bool> ]
    [ State = <string> { Running | Stopped } ]
    [ DependsOn = <string[]> ]
}
```

## <a name="properties"></a><span data-ttu-id="8f269-106">Propriedades</span><span class="sxs-lookup"><span data-stu-id="8f269-106">Properties</span></span>

|<span data-ttu-id="8f269-107">Propriedade</span><span class="sxs-lookup"><span data-stu-id="8f269-107">Property</span></span> |<span data-ttu-id="8f269-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="8f269-108">Description</span></span> |
|---|---|
|<span data-ttu-id="8f269-109">Nome</span><span class="sxs-lookup"><span data-stu-id="8f269-109">Name</span></span> |<span data-ttu-id="8f269-110">O nome do serviço/daemon que será configurado.</span><span class="sxs-lookup"><span data-stu-id="8f269-110">The name of the service/daemon to configure.</span></span> |
|<span data-ttu-id="8f269-111">Controlador</span><span class="sxs-lookup"><span data-stu-id="8f269-111">Controller</span></span> |<span data-ttu-id="8f269-112">O tipo de controlador de serviço que deve ser usado ao configurar o serviço.</span><span class="sxs-lookup"><span data-stu-id="8f269-112">The type of service controller to use when configuring the service.</span></span> |
|<span data-ttu-id="8f269-113">Habilitada</span><span class="sxs-lookup"><span data-stu-id="8f269-113">Enabled</span></span> |<span data-ttu-id="8f269-114">Indica se o serviço começa na inicialização.</span><span class="sxs-lookup"><span data-stu-id="8f269-114">Indicates whether the service starts on boot.</span></span> |
|<span data-ttu-id="8f269-115">Estado</span><span class="sxs-lookup"><span data-stu-id="8f269-115">State</span></span> |<span data-ttu-id="8f269-116">Indica se o serviço está em execução.</span><span class="sxs-lookup"><span data-stu-id="8f269-116">Indicates whether the service is running.</span></span> <span data-ttu-id="8f269-117">Defina essa propriedade como **Stopped** para garantir que o serviço não esteja em execução.</span><span class="sxs-lookup"><span data-stu-id="8f269-117">Set this property to **Stopped** to ensure that the service is not running.</span></span> <span data-ttu-id="8f269-118">Defina-a como **Running** para garantir que o serviço esteja em execução.</span><span class="sxs-lookup"><span data-stu-id="8f269-118">Set it to **Running** to ensure that the service is running.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="8f269-119">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="8f269-119">Common properties</span></span>

|<span data-ttu-id="8f269-120">Propriedade</span><span class="sxs-lookup"><span data-stu-id="8f269-120">Property</span></span> |<span data-ttu-id="8f269-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="8f269-121">Description</span></span> |
|---|---|
|<span data-ttu-id="8f269-122">DependsOn</span><span class="sxs-lookup"><span data-stu-id="8f269-122">DependsOn</span></span> |<span data-ttu-id="8f269-123">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="8f269-123">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="8f269-124">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="8f269-124">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |

## <a name="additional-information"></a><span data-ttu-id="8f269-125">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="8f269-125">Additional Information</span></span>

<span data-ttu-id="8f269-126">O recurso **nxService** não criará uma definição de serviço ou um script para o serviço se não existir.</span><span class="sxs-lookup"><span data-stu-id="8f269-126">The **nxService** resource will not create a service definition or script for the service if it does not exist.</span></span> <span data-ttu-id="8f269-127">É possível usar o recurso **nxFile** de Configuração de Estado Desejado do PowerShell para gerenciar a existência ou o conteúdo do arquivo ou script de definição de serviço.</span><span class="sxs-lookup"><span data-stu-id="8f269-127">You can use the PowerShell Desired State Configuration **nxFile** Resource resource to manage the existence or contents of the service definition file or script.</span></span>

## <a name="example"></a><span data-ttu-id="8f269-128">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8f269-128">Example</span></span>

<span data-ttu-id="8f269-129">O exemplo a seguir mostra a configuração do serviço 'httpd' (para o Apache HTTP Server), registrado com o controlador de serviço **SystemD**.</span><span class="sxs-lookup"><span data-stu-id="8f269-129">The following example shows configuration of the 'httpd' service (for Apache HTTP Server), registered with the **SystemD** service controller.</span></span>

```powershell
Import-DSCResource -Module nx

Node $node
{
    #Apache Service
    nxService ApacheService {
        Name = 'httpd'
        State = 'running'
        Enabled = $true
        Controller = 'systemd'
    }
}
```