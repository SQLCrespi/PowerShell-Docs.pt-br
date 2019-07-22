---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Recurso de DSC WaitForAll
ms.openlocfilehash: c1125b7c5b68b9b520ed052800b6a2abf4e53b85
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67726872"
---
# <a name="dsc-waitforall-resource"></a><span data-ttu-id="43223-103">Recurso de DSC WaitForAll</span><span class="sxs-lookup"><span data-stu-id="43223-103">DSC WaitForAll Resource</span></span>

> <span data-ttu-id="43223-104">Aplica-se a: Windows PowerShell 5.0 e posterior</span><span class="sxs-lookup"><span data-stu-id="43223-104">Applies To: Windows PowerShell 5.0 and later</span></span>

<span data-ttu-id="43223-105">O recurso de DSC (Desired State Configuration) **WaitForAll** pode ser usado dentro de um bloco de nó em uma [configuração DSC](../../../configurations/configurations.md) para especificar dependências em configurações em outros nós.</span><span class="sxs-lookup"><span data-stu-id="43223-105">The **WaitForAll** Desired State Configuration (DSC) resource can be used within a node block in a [DSC configuration](../../../configurations/configurations.md) to specify dependencies on configurations on other nodes.</span></span>

<span data-ttu-id="43223-106">Esse recurso terá êxito se o recurso especificado pela propriedade **ResourceName** estiver no estado desejado em todos os nós de destino definidos na propriedade **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="43223-106">This resource succeeds if the resource specified by the **ResourceName** property is in the desired state on all target nodes defined in the **NodeName** property.</span></span>

> [!NOTE]
> <span data-ttu-id="43223-107">O recurso **WaitForAll** usa o Gerenciamento Remoto do Windows para verificar o estado dos outros nós.</span><span class="sxs-lookup"><span data-stu-id="43223-107">**WaitForAll** resource uses Windows Remote Management to check the state of other Nodes.</span></span>
> <span data-ttu-id="43223-108">Para obter mais informações sobre os requisitos de porta e segurança do WinRM, confira [Considerações sobre segurança da comunicação remota do PowerShell](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).</span><span class="sxs-lookup"><span data-stu-id="43223-108">For more information about port and security requirements for WinRM, see [PowerShell Remoting Security Considerations](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).</span></span>

## <a name="syntax"></a><span data-ttu-id="43223-109">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="43223-109">Syntax</span></span>

```
WaitForAll [string] #ResourceName
{
    ResourceName = [string]
    NodeName = [string]
    [ RetryIntervalSec = [Uint64] ]
    [ RetryCount = [Uint32] ]
    [ ThrottleLimit = [Uint32]]
    [ DependsOn = [string[]] ]
}
```

## <a name="properties"></a><span data-ttu-id="43223-110">Propriedades</span><span class="sxs-lookup"><span data-stu-id="43223-110">Properties</span></span>

|  <span data-ttu-id="43223-111">Propriedade</span><span class="sxs-lookup"><span data-stu-id="43223-111">Property</span></span>  |  <span data-ttu-id="43223-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="43223-112">Description</span></span>   |
|---|---|
| <span data-ttu-id="43223-113">ResourceName</span><span class="sxs-lookup"><span data-stu-id="43223-113">ResourceName</span></span>| <span data-ttu-id="43223-114">O nome do recurso do qual dependerá.</span><span class="sxs-lookup"><span data-stu-id="43223-114">The resource name to depend on.</span></span> <span data-ttu-id="43223-115">Se esse recurso pertence a uma configuração diferente, formate o nome como "[__TipoDoRecurso__]__NomeDoRecurso__::[__NomeDaConfiguração__]::[__NomeDaConfiguração__]"</span><span class="sxs-lookup"><span data-stu-id="43223-115">If this resource belongs to a different configuration, format the name as "[__ResourceType__]__ResourceName__::[__ConfigurationName__]::[__ConfigurationName__]"</span></span>|
| <span data-ttu-id="43223-116">NodeName</span><span class="sxs-lookup"><span data-stu-id="43223-116">NodeName</span></span>| <span data-ttu-id="43223-117">Os nós de destino do recurso do qual dependerá.</span><span class="sxs-lookup"><span data-stu-id="43223-117">The target nodes of the resource to depend on.</span></span>|
| <span data-ttu-id="43223-118">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="43223-118">RetryIntervalSec</span></span>| <span data-ttu-id="43223-119">O número de segundos antes de tentar novamente.</span><span class="sxs-lookup"><span data-stu-id="43223-119">The number of seconds before retrying.</span></span> <span data-ttu-id="43223-120">O mínimo é 1.</span><span class="sxs-lookup"><span data-stu-id="43223-120">Minimum is 1.</span></span>|
| <span data-ttu-id="43223-121">RetryCount</span><span class="sxs-lookup"><span data-stu-id="43223-121">RetryCount</span></span>| <span data-ttu-id="43223-122">O número máximo de tentativas.</span><span class="sxs-lookup"><span data-stu-id="43223-122">The maximum number of times to retry.</span></span>|
| <span data-ttu-id="43223-123">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="43223-123">ThrottleLimit</span></span>| <span data-ttu-id="43223-124">O número de máquinas para conectar-se simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="43223-124">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="43223-125">O padrão é new-cimsession padrão.</span><span class="sxs-lookup"><span data-stu-id="43223-125">Default is new-cimsession default.</span></span>|
| <span data-ttu-id="43223-126">DependsOn</span><span class="sxs-lookup"><span data-stu-id="43223-126">DependsOn</span></span> | <span data-ttu-id="43223-127">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="43223-127">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="43223-128">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for __ResourceName__ e seu tipo for __ResourceType__, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="43223-128">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|

## <a name="example"></a><span data-ttu-id="43223-129">Exemplo</span><span class="sxs-lookup"><span data-stu-id="43223-129">Example</span></span>

<span data-ttu-id="43223-130">Para obter um exemplo de como usar esse recurso, consulte [Especificando dependências de nó cruzado](../../../configurations/crossNodeDependencies.md)</span><span class="sxs-lookup"><span data-stu-id="43223-130">For an example of how to use this resource, see [Specifying cross-node dependencies](../../../configurations/crossNodeDependencies.md)</span></span>
