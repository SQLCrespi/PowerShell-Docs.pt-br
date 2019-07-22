---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Recurso de DSC WaitForSome
ms.openlocfilehash: 2260f37002171154a6f2c3996b2af1bd9120039d
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67726774"
---
# <a name="dsc-waitforsome-resource"></a><span data-ttu-id="94e29-103">Recurso de DSC WaitForSome</span><span class="sxs-lookup"><span data-stu-id="94e29-103">DSC WaitForSome Resource</span></span>

> <span data-ttu-id="94e29-104">Aplica-se a: Windows PowerShell 5.0 e posterior</span><span class="sxs-lookup"><span data-stu-id="94e29-104">Applies To: Windows PowerShell 5.0 and later</span></span>

<span data-ttu-id="94e29-105">O recurso de DSC (Desired State Configuration) **WaitForSome** pode ser usado dentro de um bloco de nó em uma [configuração DSC](../../../configurations/configurations.md) para especificar dependências de configurações em outros nós.</span><span class="sxs-lookup"><span data-stu-id="94e29-105">The **WaitForSome** Desired State Configuration (DSC) resource can be used within a node block in a [DSC configuration](../../../configurations/configurations.md) to specify dependencies on configurations on other nodes.</span></span>

<span data-ttu-id="94e29-106">O recurso terá êxito se o recurso especificado pela propriedade **ResourceName** estiver no estado desejado em um número mínimo de nós (especificado por **NodeCount**) definidos pela propriedade **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="94e29-106">This resource succeeds if the resource specified by the **ResourceName** property is in the desired state on a minimum number of nodes (specified by **NodeCount**) defined by the **NodeName** property.</span></span>

> [!NOTE]
> <span data-ttu-id="94e29-107">O recurso **WaitForSome** usa o Gerenciamento Remoto do Windows para verificar o estado dos outros nós.</span><span class="sxs-lookup"><span data-stu-id="94e29-107">**WaitForSome** resource uses Windows Remote Management to check the state of other Nodes.</span></span>
> <span data-ttu-id="94e29-108">Para obter mais informações sobre os requisitos de porta e segurança do WinRM, confira [Considerações sobre segurança da comunicação remota do PowerShell](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).</span><span class="sxs-lookup"><span data-stu-id="94e29-108">For more information about port and security requirements for WinRM, see [PowerShell Remoting Security Considerations](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).</span></span>

## <a name="syntax"></a><span data-ttu-id="94e29-109">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="94e29-109">Syntax</span></span>

```
WaitForSome [String] #ResourceName
{
    NodeCount = [UInt32]
    NodeName = [string[]]
    ResourceName = [string]
    [DependsOn = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
    [RetryCount = [UInt32]]
    [RetryIntervalSec = [UInt64]]
    [ThrottleLimit = [UInt32]]
}
```

## <a name="properties"></a><span data-ttu-id="94e29-110">Propriedades</span><span class="sxs-lookup"><span data-stu-id="94e29-110">Properties</span></span>

|  <span data-ttu-id="94e29-111">Propriedade</span><span class="sxs-lookup"><span data-stu-id="94e29-111">Property</span></span>  |  <span data-ttu-id="94e29-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="94e29-112">Description</span></span>   |
|---|---|
| <span data-ttu-id="94e29-113">NodeCount</span><span class="sxs-lookup"><span data-stu-id="94e29-113">NodeCount</span></span>| <span data-ttu-id="94e29-114">O número mínimo de nós que devem estar no estado desejado para que esse recurso tenha êxito.</span><span class="sxs-lookup"><span data-stu-id="94e29-114">The minimum number of nodes that must be in the desired state for this resource to succeed.</span></span>|
| <span data-ttu-id="94e29-115">NodeName</span><span class="sxs-lookup"><span data-stu-id="94e29-115">NodeName</span></span>| <span data-ttu-id="94e29-116">Os nós de destino do recurso do qual dependerá.</span><span class="sxs-lookup"><span data-stu-id="94e29-116">The target nodes of the resource to depend on.</span></span>|
| <span data-ttu-id="94e29-117">ResourceName</span><span class="sxs-lookup"><span data-stu-id="94e29-117">ResourceName</span></span>| <span data-ttu-id="94e29-118">O nome do recurso do qual dependerá.</span><span class="sxs-lookup"><span data-stu-id="94e29-118">The resource name to depend on.</span></span> <span data-ttu-id="94e29-119">Se esse recurso pertence a uma configuração diferente, formate o nome como "[__TipoDoRecurso__]__NomeDoRecurso__::[__NomeDaConfiguração__]::[__NomeDaConfiguração__]"</span><span class="sxs-lookup"><span data-stu-id="94e29-119">If this resource belongs to a different configuration, format the name as "[__ResourceType__]__ResourceName__::[__ConfigurationName__]::[__ConfigurationName__]"</span></span>|
| <span data-ttu-id="94e29-120">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="94e29-120">RetryIntervalSec</span></span>| <span data-ttu-id="94e29-121">O número de segundos antes de tentar novamente.</span><span class="sxs-lookup"><span data-stu-id="94e29-121">The number of seconds before retrying.</span></span> <span data-ttu-id="94e29-122">O mínimo é 1.</span><span class="sxs-lookup"><span data-stu-id="94e29-122">Minimum is 1.</span></span>|
| <span data-ttu-id="94e29-123">RetryCount</span><span class="sxs-lookup"><span data-stu-id="94e29-123">RetryCount</span></span>| <span data-ttu-id="94e29-124">O número máximo de tentativas.</span><span class="sxs-lookup"><span data-stu-id="94e29-124">The maximum number of times to retry.</span></span>|
| <span data-ttu-id="94e29-125">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="94e29-125">ThrottleLimit</span></span>| <span data-ttu-id="94e29-126">O número de máquinas para conectar-se simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="94e29-126">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="94e29-127">O padrão é new-cimsession padrão.</span><span class="sxs-lookup"><span data-stu-id="94e29-127">Default is new-cimsession default.</span></span>|
| <span data-ttu-id="94e29-128">DependsOn</span><span class="sxs-lookup"><span data-stu-id="94e29-128">DependsOn</span></span> | <span data-ttu-id="94e29-129">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="94e29-129">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="94e29-130">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for __ResourceName__ e seu tipo for __ResourceType__, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="94e29-130">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|
| <span data-ttu-id="94e29-131">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="94e29-131">PsDscRunAsCredential</span></span> | <span data-ttu-id="94e29-132">Confira [Usar DSC com credenciais do usuário](https://docs.microsoft.com/powershell/dsc/runasuser)</span><span class="sxs-lookup"><span data-stu-id="94e29-132">See [Using DSC with User Credentials](https://docs.microsoft.com/powershell/dsc/runasuser)</span></span> |

## <a name="example"></a><span data-ttu-id="94e29-133">Exemplo</span><span class="sxs-lookup"><span data-stu-id="94e29-133">Example</span></span>

<span data-ttu-id="94e29-134">Para obter um exemplo de como usar esse recurso, consulte [Especificando dependências de nó cruzado](../../../configurations/crossNodeDependencies.md)</span><span class="sxs-lookup"><span data-stu-id="94e29-134">For an example of how to use this resource, see [Specifying cross-node dependencies](../../../configurations/crossNodeDependencies.md)</span></span>
