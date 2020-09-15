---
ms.date: 07/16/2020
keywords: DSC,powershell,configuração,instalação
title: Recurso de DSC WaitForAll
ms.openlocfilehash: a0cf553af96ecc3df4968581f8f393b72fc3dabf
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464359"
---
# <a name="dsc-waitforall-resource"></a><span data-ttu-id="367e5-103">Recurso de DSC WaitForAll</span><span class="sxs-lookup"><span data-stu-id="367e5-103">DSC WaitForAll Resource</span></span>

> <span data-ttu-id="367e5-104">Aplica-se a: Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="367e5-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="367e5-105">O recurso de DSC (Desired State Configuration) **WaitForAll** pode ser usado dentro de um bloco de nó em uma [configuração DSC](../../../configurations/configurations.md) para especificar dependências em configurações em outros nós.</span><span class="sxs-lookup"><span data-stu-id="367e5-105">The **WaitForAll** Desired State Configuration (DSC) resource can be used within a node block in a [DSC configuration](../../../configurations/configurations.md) to specify dependencies on configurations on other nodes.</span></span>

<span data-ttu-id="367e5-106">Esse recurso terá êxito se o recurso especificado pela propriedade **ResourceName** estiver no estado desejado em todos os nós de destino definidos na propriedade **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="367e5-106">This resource succeeds if the resource specified by the **ResourceName** property is in the desired state on all target nodes defined in the **NodeName** property.</span></span>

> [!NOTE]
> <span data-ttu-id="367e5-107">O recurso **WaitForAll** usa o Gerenciamento Remoto do Windows para verificar o estado dos outros nós.</span><span class="sxs-lookup"><span data-stu-id="367e5-107">**WaitForAll** resource uses Windows Remote Management to check the state of other Nodes.</span></span> <span data-ttu-id="367e5-108">Para obter mais informações sobre os requisitos de porta e segurança do WinRM, confira [Considerações sobre segurança da comunicação remota do PowerShell](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).</span><span class="sxs-lookup"><span data-stu-id="367e5-108">For more information about port and security requirements for WinRM, see [PowerShell Remoting Security Considerations](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).</span></span>

## <a name="syntax"></a><span data-ttu-id="367e5-109">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="367e5-109">Syntax</span></span>

```Syntax
WaitForAll [string] #ResourceName
{
    ResourceName = [string]
    NodeName = [string[]]
    [ RetryIntervalSec = [Uint64] ]
    [ RetryCount = [Uint32] ]
    [ ThrottleLimit = [Uint32]]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="367e5-110">Propriedades</span><span class="sxs-lookup"><span data-stu-id="367e5-110">Properties</span></span>

|<span data-ttu-id="367e5-111">Propriedade</span><span class="sxs-lookup"><span data-stu-id="367e5-111">Property</span></span> |<span data-ttu-id="367e5-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="367e5-112">Description</span></span> |
|---|---|
|<span data-ttu-id="367e5-113">ResourceName</span><span class="sxs-lookup"><span data-stu-id="367e5-113">ResourceName</span></span> |<span data-ttu-id="367e5-114">O nome do recurso do qual dependerá.</span><span class="sxs-lookup"><span data-stu-id="367e5-114">The resource name to depend on.</span></span> <span data-ttu-id="367e5-115">Se esse recurso pertencer a uma configuração diferente, formate o nome como `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]`.</span><span class="sxs-lookup"><span data-stu-id="367e5-115">If this resource belongs to a different configuration, format the name as `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]`.</span></span> |
|<span data-ttu-id="367e5-116">NodeName</span><span class="sxs-lookup"><span data-stu-id="367e5-116">NodeName</span></span> |<span data-ttu-id="367e5-117">Os nós de destino do recurso do qual dependerá.</span><span class="sxs-lookup"><span data-stu-id="367e5-117">The target nodes of the resource to depend on.</span></span> |
|<span data-ttu-id="367e5-118">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="367e5-118">RetryIntervalSec</span></span> |<span data-ttu-id="367e5-119">O número de segundos antes de tentar novamente.</span><span class="sxs-lookup"><span data-stu-id="367e5-119">The number of seconds before retrying.</span></span> <span data-ttu-id="367e5-120">O mínimo é 1.</span><span class="sxs-lookup"><span data-stu-id="367e5-120">Minimum is 1.</span></span> |
|<span data-ttu-id="367e5-121">RetryCount</span><span class="sxs-lookup"><span data-stu-id="367e5-121">RetryCount</span></span> |<span data-ttu-id="367e5-122">O número máximo de tentativas.</span><span class="sxs-lookup"><span data-stu-id="367e5-122">The maximum number of times to retry.</span></span> |
|<span data-ttu-id="367e5-123">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="367e5-123">ThrottleLimit</span></span> |<span data-ttu-id="367e5-124">O número de máquinas para conectar-se simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="367e5-124">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="367e5-125">O padrão é `New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="367e5-125">Default is `New-CimSession` default.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="367e5-126">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="367e5-126">Common properties</span></span>

|<span data-ttu-id="367e5-127">Propriedade</span><span class="sxs-lookup"><span data-stu-id="367e5-127">Property</span></span> |<span data-ttu-id="367e5-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="367e5-128">Description</span></span> |
|---|---|
|<span data-ttu-id="367e5-129">DependsOn</span><span class="sxs-lookup"><span data-stu-id="367e5-129">DependsOn</span></span> |<span data-ttu-id="367e5-130">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="367e5-130">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="367e5-131">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="367e5-131">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="367e5-132">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="367e5-132">PsDscRunAsCredential</span></span> |<span data-ttu-id="367e5-133">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="367e5-133">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="367e5-134">A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais.</span><span class="sxs-lookup"><span data-stu-id="367e5-134">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="367e5-135">Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="367e5-135">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="367e5-136">Exemplo</span><span class="sxs-lookup"><span data-stu-id="367e5-136">Example</span></span>

<span data-ttu-id="367e5-137">Para obter um exemplo de como usar esse recurso, consulte [Especificando dependências de nó cruzado](../../../configurations/crossNodeDependencies.md)</span><span class="sxs-lookup"><span data-stu-id="367e5-137">For an example of how to use this resource, see [Specifying cross-node dependencies](../../../configurations/crossNodeDependencies.md)</span></span>
