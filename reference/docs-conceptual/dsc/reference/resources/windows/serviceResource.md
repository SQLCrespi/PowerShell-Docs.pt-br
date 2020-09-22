---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso Service de DSC
ms.openlocfilehash: f936f58ffd00f84d8c6d5d41d93378eaa8db5879
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463577"
---
# <a name="dsc-service-resource"></a><span data-ttu-id="e5ad1-103">Recurso Service de DSC</span><span class="sxs-lookup"><span data-stu-id="e5ad1-103">DSC Service Resource</span></span>

> <span data-ttu-id="e5ad1-104">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="e5ad1-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="e5ad1-105">O recurso **Service** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para gerenciar serviços no nó de destino.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-105">The **Service** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage services on the target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="e5ad1-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e5ad1-106">Syntax</span></span>

```Syntax
Service [string] #ResourceName
{
    Name = [string]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ Credential = [PSCredential] ]
    [ StartupTimeout = [uint32]]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ State = [string] { Ignore | Running | Stopped }  ]
    [ Dependencies = [string[]] ]
    [ Description = [string] ]
    [ DesktopInteract = [boolean]]
    [ DisplayName = [string] ]
    [ Path = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
    [ TerminateTimeout = [uint32] ]
}
```

## <a name="properties"></a><span data-ttu-id="e5ad1-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="e5ad1-107">Properties</span></span>

|<span data-ttu-id="e5ad1-108">Propriedade</span><span class="sxs-lookup"><span data-stu-id="e5ad1-108">Property</span></span> |<span data-ttu-id="e5ad1-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="e5ad1-109">Description</span></span> |
|---|---|
|<span data-ttu-id="e5ad1-110">Nome</span><span class="sxs-lookup"><span data-stu-id="e5ad1-110">Name</span></span> |<span data-ttu-id="e5ad1-111">Indica o nome do serviço.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-111">Indicates the service name.</span></span> <span data-ttu-id="e5ad1-112">Observe que, às vezes, é diferente do nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-112">Note that sometimes this is different from the display name.</span></span> <span data-ttu-id="e5ad1-113">É possível obter uma lista dos serviços e seus estados atuais com o cmdlet `Get-Service`.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-113">You can get a list of the services and their current state with the `Get-Service` cmdlet.</span></span> |
|<span data-ttu-id="e5ad1-114">BuiltInAccount</span><span class="sxs-lookup"><span data-stu-id="e5ad1-114">BuiltInAccount</span></span> |<span data-ttu-id="e5ad1-115">Indica a conta de entrada que deve ser usada para o serviço.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-115">Indicates the sign-in account to use for the service.</span></span> <span data-ttu-id="e5ad1-116">Os valores permitidos para essa propriedade são: **LocalService**, **LocalSystem** e **NetworkService**.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-116">The values that are allowed for this property are: **LocalService**, **LocalSystem**, and **NetworkService**.</span></span> |
|<span data-ttu-id="e5ad1-117">Credencial</span><span class="sxs-lookup"><span data-stu-id="e5ad1-117">Credential</span></span> |<span data-ttu-id="e5ad1-118">Indica as credenciais para a conta em que o serviço será executado.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-118">Indicates credentials for the account that the service will run under.</span></span> <span data-ttu-id="e5ad1-119">Essa propriedade e a propriedade **BuiltinAccount** não podem ser usadas juntas.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-119">This property and the **BuiltinAccount** property cannot be used together.</span></span> |
|<span data-ttu-id="e5ad1-120">StartupTimeout</span><span class="sxs-lookup"><span data-stu-id="e5ad1-120">StartupTimeout</span></span> | <span data-ttu-id="e5ad1-121">O tempo de espera para o serviço ser executado em milissegundos.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-121">The time to wait for the service to be running in milliseconds.</span></span>|
|<span data-ttu-id="e5ad1-122">StartupType</span><span class="sxs-lookup"><span data-stu-id="e5ad1-122">StartupType</span></span> |<span data-ttu-id="e5ad1-123">Indica o tipo de inicialização para o serviço.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-123">Indicates the startup type for the service.</span></span> <span data-ttu-id="e5ad1-124">Os valores permitidos para essa propriedade são: **Automático**, **Desabilitado** e **Manual**.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-124">The values that are allowed for this property are: **Automatic**, **Disabled**, and **Manual**.</span></span> |
|<span data-ttu-id="e5ad1-125">Estado</span><span class="sxs-lookup"><span data-stu-id="e5ad1-125">State</span></span> |<span data-ttu-id="e5ad1-126">Indica o estado que você deseja garantir para o serviço.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-126">Indicates the state you want to ensure for the service.</span></span> <span data-ttu-id="e5ad1-127">Os valores são: **Em execução** ou **Parado**.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-127">The values are: **Running** or **Stopped**.</span></span> |
|<span data-ttu-id="e5ad1-128">TerminateTimeout</span><span class="sxs-lookup"><span data-stu-id="e5ad1-128">TerminateTimeout</span></span> |<span data-ttu-id="e5ad1-129">O tempo de espera para o serviço ser interrompido em milissegundos.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-129">The time to wait for the service to be stopped in milliseconds.</span></span>|
|<span data-ttu-id="e5ad1-130">Dependências</span><span class="sxs-lookup"><span data-stu-id="e5ad1-130">Dependencies</span></span> | <span data-ttu-id="e5ad1-131">Uma matriz dos nomes das dependências que o serviço deve ter.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-131">An array of the names of the dependencies the service should have.</span></span> |
|<span data-ttu-id="e5ad1-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="e5ad1-132">Description</span></span> |<span data-ttu-id="e5ad1-133">Indica a descrição do serviço de destino.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-133">Indicates the description of the target service.</span></span> |
|<span data-ttu-id="e5ad1-134">DesktopInteract</span><span class="sxs-lookup"><span data-stu-id="e5ad1-134">DesktopInteract</span></span> | <span data-ttu-id="e5ad1-135">Indica se o serviço deve poder se comunicar ou não com uma janela na área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-135">Indicates whether or not the service should be able to communicate with a window on the desktop.</span></span> <span data-ttu-id="e5ad1-136">Precisa ser false para que os serviços não sejam executados como LocalSystem.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-136">Must be false for services not running as LocalSystem.</span></span>|
|<span data-ttu-id="e5ad1-137">DisplayName</span><span class="sxs-lookup"><span data-stu-id="e5ad1-137">DisplayName</span></span> |<span data-ttu-id="e5ad1-138">Indica o nome de exibição do serviço de destino.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-138">Indicates the display name of the target service.</span></span> |
|<span data-ttu-id="e5ad1-139">Caminho</span><span class="sxs-lookup"><span data-stu-id="e5ad1-139">Path</span></span> |<span data-ttu-id="e5ad1-140">Indica o caminho para o arquivo binário para um novo serviço.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-140">Indicates the path to the binary file for a new service.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="e5ad1-141">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="e5ad1-141">Common properties</span></span>

|<span data-ttu-id="e5ad1-142">Propriedade</span><span class="sxs-lookup"><span data-stu-id="e5ad1-142">Property</span></span> |<span data-ttu-id="e5ad1-143">Descrição</span><span class="sxs-lookup"><span data-stu-id="e5ad1-143">Description</span></span> |
|---|---|
|<span data-ttu-id="e5ad1-144">DependsOn</span><span class="sxs-lookup"><span data-stu-id="e5ad1-144">DependsOn</span></span> |<span data-ttu-id="e5ad1-145">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-145">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="e5ad1-146">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-146">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="e5ad1-147">Ensure</span><span class="sxs-lookup"><span data-stu-id="e5ad1-147">Ensure</span></span> |<span data-ttu-id="e5ad1-148">Indica se o serviço de destino existe no sistema.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-148">Indicates whether the target service exists on the system.</span></span> <span data-ttu-id="e5ad1-149">Defina essa propriedade como **Ausente** para garantir que o serviço de destino não exista.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-149">Set this property to **Absent** to ensure that the target service does not exist.</span></span> <span data-ttu-id="e5ad1-150">Defini-la como **Present** garantirá que o serviço de destino exista.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-150">Setting it to **Present** ensures that target service exists.</span></span> <span data-ttu-id="e5ad1-151">O valor padrão é **Present**.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-151">The default value is **Present**.</span></span> |
|<span data-ttu-id="e5ad1-152">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="e5ad1-152">PsDscRunAsCredential</span></span> |<span data-ttu-id="e5ad1-153">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-153">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="e5ad1-154">A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais.</span><span class="sxs-lookup"><span data-stu-id="e5ad1-154">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="e5ad1-155">Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="e5ad1-155">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="e5ad1-156">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e5ad1-156">Example</span></span>

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
