---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Recurso de DSC WaitForAny
ms.openlocfilehash: 55869f665837b422c006f4cfb3e91366fac60362
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076813"
---
# <a name="dsc-waitforany-resource"></a><span data-ttu-id="824ba-103">Recurso de DSC WaitForAny</span><span class="sxs-lookup"><span data-stu-id="824ba-103">DSC WaitForAny Resource</span></span>

> <span data-ttu-id="824ba-104">Aplica-se a: Windows PowerShell 5.1 e posterior</span><span class="sxs-lookup"><span data-stu-id="824ba-104">Applies To: Windows PowerShell 5.1 and later</span></span>

<span data-ttu-id="824ba-105">O recurso de DSC (Desired State Configuration) **WaitForAny** pode ser usado dentro de um bloco de nó em uma [configuração DSC](../../../configurations/configurations.md) para especificar dependências de configurações em outros nós.</span><span class="sxs-lookup"><span data-stu-id="824ba-105">The **WaitForAny** Desired State Configuration (DSC) resource can be used within a node block in a [DSC configuration](../../../configurations/configurations.md) to specify dependencies on configurations on other nodes.</span></span>

<span data-ttu-id="824ba-106">Esse recurso terá êxito se o recurso especificado pela propriedade **ResourceName** estiver no estado desejado em qualquer nó de destino definido na propriedade **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="824ba-106">This resource succeeds if the resource specified by the **ResourceName** property is in the desired state on any target nodes defined in the **NodeName** property.</span></span>


## <a name="syntax"></a><span data-ttu-id="824ba-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="824ba-107">Syntax</span></span>

```
WaitForAny [string] #ResourceName
{
    ResourceName = [string]
    NodeName = [string]
    [ RetryIntervalSec = [Uint64] ]
    [ RetryCount = [Uint32] ]
    [ ThrottleLimit = [Uint32]]
    [ DependsOn = [string[]] ]
}
```

## <a name="properties"></a><span data-ttu-id="824ba-108">Propriedades</span><span class="sxs-lookup"><span data-stu-id="824ba-108">Properties</span></span>

|  <span data-ttu-id="824ba-109">Propriedade</span><span class="sxs-lookup"><span data-stu-id="824ba-109">Property</span></span>  |  <span data-ttu-id="824ba-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="824ba-110">Description</span></span>   |
|---|---|
| <span data-ttu-id="824ba-111">ResourceName</span><span class="sxs-lookup"><span data-stu-id="824ba-111">ResourceName</span></span>| <span data-ttu-id="824ba-112">O nome do recurso do qual dependerá.</span><span class="sxs-lookup"><span data-stu-id="824ba-112">The resource name to depend on.</span></span> <span data-ttu-id="824ba-113">Se esse recurso pertence a uma configuração diferente, formate o nome como "[__TipoDoRecurso__]__NomeDoRecurso__::[__NomeDaConfiguração__]::[__NomeDaConfiguração__]"</span><span class="sxs-lookup"><span data-stu-id="824ba-113">If this resource belongs to a different configuration, format the name as "[__ResourceType__]__ResourceName__::[__ConfigurationName__]::[__ConfigurationName__]"</span></span>|
| <span data-ttu-id="824ba-114">NodeName</span><span class="sxs-lookup"><span data-stu-id="824ba-114">NodeName</span></span>| <span data-ttu-id="824ba-115">Os nós de destino do recurso do qual dependerá.</span><span class="sxs-lookup"><span data-stu-id="824ba-115">The target nodes of the resource to depend on.</span></span>|
| <span data-ttu-id="824ba-116">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="824ba-116">RetryIntervalSec</span></span>| <span data-ttu-id="824ba-117">O número de segundos antes de tentar novamente.</span><span class="sxs-lookup"><span data-stu-id="824ba-117">The number of seconds before retrying.</span></span> <span data-ttu-id="824ba-118">O mínimo é 1.</span><span class="sxs-lookup"><span data-stu-id="824ba-118">Minimum is 1.</span></span>|
| <span data-ttu-id="824ba-119">RetryCount</span><span class="sxs-lookup"><span data-stu-id="824ba-119">RetryCount</span></span>| <span data-ttu-id="824ba-120">O número máximo de tentativas.</span><span class="sxs-lookup"><span data-stu-id="824ba-120">The maximum number of times to retry.</span></span>|
| <span data-ttu-id="824ba-121">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="824ba-121">ThrottleLimit</span></span>| <span data-ttu-id="824ba-122">O número de máquinas para conectar-se simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="824ba-122">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="824ba-123">O padrão é new-cimsession padrão.</span><span class="sxs-lookup"><span data-stu-id="824ba-123">Default is new-cimsession default.</span></span>|
| <span data-ttu-id="824ba-124">DependsOn</span><span class="sxs-lookup"><span data-stu-id="824ba-124">DependsOn</span></span> | <span data-ttu-id="824ba-125">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="824ba-125">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="824ba-126">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for __ResourceName__ e seu tipo for __ResourceType__, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="824ba-126">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|

## <a name="example"></a><span data-ttu-id="824ba-127">Exemplo</span><span class="sxs-lookup"><span data-stu-id="824ba-127">Example</span></span>

<span data-ttu-id="824ba-128">Para obter um exemplo de como usar esse recurso, consulte [Especificando dependências de nó cruzado](../../../configurations/crossNodeDependencies.md)</span><span class="sxs-lookup"><span data-stu-id="824ba-128">For an example of how to use this resource, see [Specifying cross-node dependencies](../../../configurations/crossNodeDependencies.md)</span></span>
