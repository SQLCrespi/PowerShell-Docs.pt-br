---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso Service de DSC
ms.openlocfilehash: 0bef6aa6d3526c9d8d92187c1e738d5c46b5665a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "71953043"
---
# <a name="dsc-service-resource"></a><span data-ttu-id="efa0b-103">Recurso Service de DSC</span><span class="sxs-lookup"><span data-stu-id="efa0b-103">DSC Service Resource</span></span>

> <span data-ttu-id="efa0b-104">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="efa0b-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="efa0b-105">O recurso **Service** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para gerenciar serviços no nó de destino.</span><span class="sxs-lookup"><span data-stu-id="efa0b-105">The **Service** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage services on the target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="efa0b-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="efa0b-106">Syntax</span></span>

```Syntax
Service [string] #ResourceName
{
    Name = [string]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ Credential = [PSCredential] ]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ State = [string] { Running | Stopped }  ]
    [ Description = [string] ]
    [ DisplayName = [string] ]
    [ Path = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="efa0b-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="efa0b-107">Properties</span></span>

|<span data-ttu-id="efa0b-108">Propriedade</span><span class="sxs-lookup"><span data-stu-id="efa0b-108">Property</span></span> |<span data-ttu-id="efa0b-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="efa0b-109">Description</span></span> |
|---|---|
|<span data-ttu-id="efa0b-110">Nome</span><span class="sxs-lookup"><span data-stu-id="efa0b-110">Name</span></span> |<span data-ttu-id="efa0b-111">Indica o nome do serviço.</span><span class="sxs-lookup"><span data-stu-id="efa0b-111">Indicates the service name.</span></span> <span data-ttu-id="efa0b-112">Observe que, às vezes, é diferente do nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="efa0b-112">Note that sometimes this is different from the display name.</span></span> <span data-ttu-id="efa0b-113">É possível obter uma lista dos serviços e seus estados atuais com o cmdlet `Get-Service`.</span><span class="sxs-lookup"><span data-stu-id="efa0b-113">You can get a list of the services and their current state with the `Get-Service` cmdlet.</span></span> |
|<span data-ttu-id="efa0b-114">BuiltInAccount</span><span class="sxs-lookup"><span data-stu-id="efa0b-114">BuiltInAccount</span></span> |<span data-ttu-id="efa0b-115">Indica a conta de entrada que deve ser usada para o serviço.</span><span class="sxs-lookup"><span data-stu-id="efa0b-115">Indicates the sign-in account to use for the service.</span></span> <span data-ttu-id="efa0b-116">Os valores permitidos para essa propriedade são: **LocalService**, **LocalSystem** e **NetworkService**.</span><span class="sxs-lookup"><span data-stu-id="efa0b-116">The values that are allowed for this property are: **LocalService**, **LocalSystem**, and **NetworkService**.</span></span> |
|<span data-ttu-id="efa0b-117">Credential</span><span class="sxs-lookup"><span data-stu-id="efa0b-117">Credential</span></span> |<span data-ttu-id="efa0b-118">Indica as credenciais para a conta em que o serviço será executado.</span><span class="sxs-lookup"><span data-stu-id="efa0b-118">Indicates credentials for the account that the service will run under.</span></span> <span data-ttu-id="efa0b-119">Essa propriedade e a propriedade **BuiltinAccount** não podem ser usadas juntas.</span><span class="sxs-lookup"><span data-stu-id="efa0b-119">This property and the **BuiltinAccount** property cannot be used together.</span></span> |
|<span data-ttu-id="efa0b-120">StartupType</span><span class="sxs-lookup"><span data-stu-id="efa0b-120">StartupType</span></span> |<span data-ttu-id="efa0b-121">Indica o tipo de inicialização para o serviço.</span><span class="sxs-lookup"><span data-stu-id="efa0b-121">Indicates the startup type for the service.</span></span> <span data-ttu-id="efa0b-122">Os valores permitidos para essa propriedade são: **Automático**, **Desabilitado** e **Manual**.</span><span class="sxs-lookup"><span data-stu-id="efa0b-122">The values that are allowed for this property are: **Automatic**, **Disabled**, and **Manual**.</span></span> |
|<span data-ttu-id="efa0b-123">Estado</span><span class="sxs-lookup"><span data-stu-id="efa0b-123">State</span></span> |<span data-ttu-id="efa0b-124">Indica o estado que você deseja garantir para o serviço.</span><span class="sxs-lookup"><span data-stu-id="efa0b-124">Indicates the state you want to ensure for the service.</span></span> <span data-ttu-id="efa0b-125">Os valores são: **Em execução** ou **Parado**.</span><span class="sxs-lookup"><span data-stu-id="efa0b-125">The values are: **Running** or **Stopped**.</span></span> |
|<span data-ttu-id="efa0b-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="efa0b-126">Description</span></span> |<span data-ttu-id="efa0b-127">Indica a descrição do serviço de destino.</span><span class="sxs-lookup"><span data-stu-id="efa0b-127">Indicates the description of the target service.</span></span> |
|<span data-ttu-id="efa0b-128">DisplayName</span><span class="sxs-lookup"><span data-stu-id="efa0b-128">DisplayName</span></span> |<span data-ttu-id="efa0b-129">Indica o nome de exibição do serviço de destino.</span><span class="sxs-lookup"><span data-stu-id="efa0b-129">Indicates the display name of the target service.</span></span> |
|<span data-ttu-id="efa0b-130">Caminho</span><span class="sxs-lookup"><span data-stu-id="efa0b-130">Path</span></span> |<span data-ttu-id="efa0b-131">Indica o caminho para o arquivo binário para um novo serviço.</span><span class="sxs-lookup"><span data-stu-id="efa0b-131">Indicates the path to the binary file for a new service.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="efa0b-132">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="efa0b-132">Common properties</span></span>

|<span data-ttu-id="efa0b-133">Propriedade</span><span class="sxs-lookup"><span data-stu-id="efa0b-133">Property</span></span> |<span data-ttu-id="efa0b-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="efa0b-134">Description</span></span> |
|---|---|
|<span data-ttu-id="efa0b-135">DependsOn</span><span class="sxs-lookup"><span data-stu-id="efa0b-135">DependsOn</span></span> |<span data-ttu-id="efa0b-136">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="efa0b-136">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="efa0b-137">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="efa0b-137">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="efa0b-138">Ensure</span><span class="sxs-lookup"><span data-stu-id="efa0b-138">Ensure</span></span> |<span data-ttu-id="efa0b-139">Indica se o serviço de destino existe no sistema.</span><span class="sxs-lookup"><span data-stu-id="efa0b-139">Indicates whether the target service exists on the system.</span></span> <span data-ttu-id="efa0b-140">Defina essa propriedade como **Ausente** para garantir que o serviço de destino não exista.</span><span class="sxs-lookup"><span data-stu-id="efa0b-140">Set this property to **Absent** to ensure that the target service does not exist.</span></span> <span data-ttu-id="efa0b-141">Defini-la como **Present** garantirá que o serviço de destino exista.</span><span class="sxs-lookup"><span data-stu-id="efa0b-141">Setting it to **Present** ensures that target service exists.</span></span> <span data-ttu-id="efa0b-142">O valor padrão é **Present**.</span><span class="sxs-lookup"><span data-stu-id="efa0b-142">The default value is **Present**.</span></span> |
|<span data-ttu-id="efa0b-143">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="efa0b-143">PsDscRunAsCredential</span></span> |<span data-ttu-id="efa0b-144">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="efa0b-144">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="efa0b-145">A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais.</span><span class="sxs-lookup"><span data-stu-id="efa0b-145">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="efa0b-146">Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="efa0b-146">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="efa0b-147">Exemplo</span><span class="sxs-lookup"><span data-stu-id="efa0b-147">Example</span></span>

```powershell
configuration ServiceTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {

        Service ServiceExample
        {
            Name        = "TermService"
            StartupType = "Manual"
            State       = "Running"
        }
    }
}
```