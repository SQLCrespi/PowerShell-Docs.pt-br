---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso de DSC WaitForSome
ms.openlocfilehash: 37c73ed4a42975194938f78de04096a988cf9846
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83561079"
---
# <a name="dsc-waitforsome-resource"></a><span data-ttu-id="dd504-103">Recurso de DSC WaitForSome</span><span class="sxs-lookup"><span data-stu-id="dd504-103">DSC WaitForSome Resource</span></span>

> <span data-ttu-id="dd504-104">Aplica-se a: Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="dd504-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="dd504-105">O recurso de DSC (Desired State Configuration) **WaitForSome** pode ser usado dentro de um bloco de nó em uma [configuração DSC](../../../configurations/configurations.md) para especificar dependências de configurações em outros nós.</span><span class="sxs-lookup"><span data-stu-id="dd504-105">The **WaitForSome** Desired State Configuration (DSC) resource can be used within a node block in a [DSC configuration](../../../configurations/configurations.md) to specify dependencies on configurations on other nodes.</span></span>

<span data-ttu-id="dd504-106">O recurso terá êxito se o recurso especificado pela propriedade **ResourceName** estiver no estado desejado em um número mínimo de nós (especificado por **NodeCount**) definidos pela propriedade **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="dd504-106">This resource succeeds if the resource specified by the **ResourceName** property is in the desired state on a minimum number of nodes (specified by **NodeCount**) defined by the **NodeName** property.</span></span>

> [!NOTE]
> <span data-ttu-id="dd504-107">O recurso **WaitForSome** usa o Gerenciamento Remoto do Windows para verificar o estado dos outros nós.</span><span class="sxs-lookup"><span data-stu-id="dd504-107">**WaitForSome** resource uses Windows Remote Management to check the state of other Nodes.</span></span> <span data-ttu-id="dd504-108">Para obter mais informações sobre os requisitos de porta e segurança do WinRM, confira [Considerações sobre segurança da comunicação remota do PowerShell](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).</span><span class="sxs-lookup"><span data-stu-id="dd504-108">For more information about port and security requirements for WinRM, see [PowerShell Remoting Security Considerations](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).</span></span>

## <a name="syntax"></a><span data-ttu-id="dd504-109">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="dd504-109">Syntax</span></span>

```Syntax
WaitForSome [String] #ResourceName
{
    NodeCount = [UInt32]
    NodeName = [string[]]
    ResourceName = [string]
    [ RetryCount = [UInt32] ]
    [ RetryIntervalSec = [UInt64] ]
    [ ThrottleLimit = [UInt32] ]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="dd504-110">Propriedades</span><span class="sxs-lookup"><span data-stu-id="dd504-110">Properties</span></span>

|<span data-ttu-id="dd504-111">Propriedade</span><span class="sxs-lookup"><span data-stu-id="dd504-111">Property</span></span> |<span data-ttu-id="dd504-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="dd504-112">Description</span></span> |
|---|---|
|<span data-ttu-id="dd504-113">NodeCount</span><span class="sxs-lookup"><span data-stu-id="dd504-113">NodeCount</span></span> |<span data-ttu-id="dd504-114">O número mínimo de nós que devem estar no estado desejado para que esse recurso tenha êxito.</span><span class="sxs-lookup"><span data-stu-id="dd504-114">The minimum number of nodes that must be in the desired state for this resource to succeed.</span></span> |
|<span data-ttu-id="dd504-115">NodeName</span><span class="sxs-lookup"><span data-stu-id="dd504-115">NodeName</span></span> |<span data-ttu-id="dd504-116">Os nós de destino do recurso do qual dependerá.</span><span class="sxs-lookup"><span data-stu-id="dd504-116">The target nodes of the resource to depend on.</span></span> |
|<span data-ttu-id="dd504-117">ResourceName</span><span class="sxs-lookup"><span data-stu-id="dd504-117">ResourceName</span></span> |<span data-ttu-id="dd504-118">O nome do recurso do qual dependerá.</span><span class="sxs-lookup"><span data-stu-id="dd504-118">The resource name to depend on.</span></span> <span data-ttu-id="dd504-119">Se esse recurso pertencer a uma configuração diferente, formate o nome como `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]`.</span><span class="sxs-lookup"><span data-stu-id="dd504-119">If this resource belongs to a different configuration, format the name as `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]`.</span></span> |
|<span data-ttu-id="dd504-120">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="dd504-120">RetryIntervalSec</span></span> |<span data-ttu-id="dd504-121">O número de segundos antes de tentar novamente.</span><span class="sxs-lookup"><span data-stu-id="dd504-121">The number of seconds before retrying.</span></span> <span data-ttu-id="dd504-122">O mínimo é 1.</span><span class="sxs-lookup"><span data-stu-id="dd504-122">Minimum is 1.</span></span> |
|<span data-ttu-id="dd504-123">RetryCount</span><span class="sxs-lookup"><span data-stu-id="dd504-123">RetryCount</span></span> |<span data-ttu-id="dd504-124">O número máximo de tentativas.</span><span class="sxs-lookup"><span data-stu-id="dd504-124">The maximum number of times to retry.</span></span> |
|<span data-ttu-id="dd504-125">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="dd504-125">ThrottleLimit</span></span> |<span data-ttu-id="dd504-126">O número de máquinas para conectar-se simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="dd504-126">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="dd504-127">O padrão é `New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="dd504-127">Default is `New-CimSession` default.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="dd504-128">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="dd504-128">Common properties</span></span>

|<span data-ttu-id="dd504-129">Propriedade</span><span class="sxs-lookup"><span data-stu-id="dd504-129">Property</span></span> |<span data-ttu-id="dd504-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="dd504-130">Description</span></span> |
|---|---|
|<span data-ttu-id="dd504-131">DependsOn</span><span class="sxs-lookup"><span data-stu-id="dd504-131">DependsOn</span></span> |<span data-ttu-id="dd504-132">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="dd504-132">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="dd504-133">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="dd504-133">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="dd504-134">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="dd504-134">PsDscRunAsCredential</span></span> |<span data-ttu-id="dd504-135">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="dd504-135">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="dd504-136">A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais.</span><span class="sxs-lookup"><span data-stu-id="dd504-136">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="dd504-137">Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="dd504-137">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="dd504-138">Exemplo</span><span class="sxs-lookup"><span data-stu-id="dd504-138">Example</span></span>

<span data-ttu-id="dd504-139">Para obter um exemplo de como usar esse recurso, consulte [Especificando dependências de nó cruzado](../../../configurations/crossNodeDependencies.md)</span><span class="sxs-lookup"><span data-stu-id="dd504-139">For an example of how to use this resource, see [Specifying cross-node dependencies](../../../configurations/crossNodeDependencies.md)</span></span>
