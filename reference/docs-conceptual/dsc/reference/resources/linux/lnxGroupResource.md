---
ms.date: 07/17/2020
keywords: DSC,powershell,configuração,instalação
title: Recurso nxGroup de DSC para Linux
ms.openlocfilehash: f196c74b94ec27818d58b59d1e489facd8ab0a65
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464427"
---
# <a name="dsc-for-linux-nxgroup-resource"></a><span data-ttu-id="ae6a6-103">Recurso nxGroup de DSC para Linux</span><span class="sxs-lookup"><span data-stu-id="ae6a6-103">DSC for Linux nxGroup Resource</span></span>

<span data-ttu-id="ae6a6-104">O recurso **nxGroup** na Configuração de Estado Desejado (DSC) do PowerShell fornece um mecanismo para gerenciar grupos locais em um nó do Linux.</span><span class="sxs-lookup"><span data-stu-id="ae6a6-104">The **nxGroup** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage local groups on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="ae6a6-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ae6a6-105">Syntax</span></span>

```Syntax
nxGroup <string> #ResourceName
{
    GroupName = <string>
    [ Members = <string[]> ]
    [ MembersToInclude = <string[]> ]
    [ MembersToExclude = <string[]> ]
    [ PreferredGroupID = <string> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present } ]
}
```

## <a name="properties"></a><span data-ttu-id="ae6a6-106">Propriedades</span><span class="sxs-lookup"><span data-stu-id="ae6a6-106">Properties</span></span>

|<span data-ttu-id="ae6a6-107">Propriedade</span><span class="sxs-lookup"><span data-stu-id="ae6a6-107">Property</span></span> |<span data-ttu-id="ae6a6-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="ae6a6-108">Description</span></span> |
|---|---|
|<span data-ttu-id="ae6a6-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="ae6a6-109">GroupName</span></span> |<span data-ttu-id="ae6a6-110">Especifica o nome do grupo para o qual você deseja garantir um estado específico.</span><span class="sxs-lookup"><span data-stu-id="ae6a6-110">Specifies the name of the group for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="ae6a6-111">Membros</span><span class="sxs-lookup"><span data-stu-id="ae6a6-111">Members</span></span> |<span data-ttu-id="ae6a6-112">Especifica os membros que formam o grupo.</span><span class="sxs-lookup"><span data-stu-id="ae6a6-112">Specifies the members that form the group.</span></span> |
|<span data-ttu-id="ae6a6-113">MembersToInclude</span><span class="sxs-lookup"><span data-stu-id="ae6a6-113">MembersToInclude</span></span> |<span data-ttu-id="ae6a6-114">Especifica os usuários que você deseja garantir que sejam membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="ae6a6-114">Specifies the users who you want to ensure are members of the group.</span></span> |
|<span data-ttu-id="ae6a6-115">MembersToExclude</span><span class="sxs-lookup"><span data-stu-id="ae6a6-115">MembersToExclude</span></span> |<span data-ttu-id="ae6a6-116">Especifica os usuários que você deseja garantir que não sejam membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="ae6a6-116">Specifies the users who you want to ensure are not members of the group.</span></span> |
|<span data-ttu-id="ae6a6-117">PreferredGroupID</span><span class="sxs-lookup"><span data-stu-id="ae6a6-117">PreferredGroupID</span></span> |<span data-ttu-id="ae6a6-118">Define a ID do grupo para o valor fornecido, se possível.</span><span class="sxs-lookup"><span data-stu-id="ae6a6-118">Sets the group id to the provided value if possible.</span></span> <span data-ttu-id="ae6a6-119">Se a ID do grupo estiver em uso no momento, a próxima ID de grupo disponível será usada.</span><span class="sxs-lookup"><span data-stu-id="ae6a6-119">If the group id is currently in use, the next available group id is used.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="ae6a6-120">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="ae6a6-120">Common properties</span></span>

|<span data-ttu-id="ae6a6-121">Propriedade</span><span class="sxs-lookup"><span data-stu-id="ae6a6-121">Property</span></span> |<span data-ttu-id="ae6a6-122">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="ae6a6-122">Description</span></span> |
|---|---|
|<span data-ttu-id="ae6a6-123">DependsOn</span><span class="sxs-lookup"><span data-stu-id="ae6a6-123">DependsOn</span></span> |<span data-ttu-id="ae6a6-124">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="ae6a6-124">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="ae6a6-125">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="ae6a6-125">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="ae6a6-126">Ensure</span><span class="sxs-lookup"><span data-stu-id="ae6a6-126">Ensure</span></span> |<span data-ttu-id="ae6a6-127">Determina se é necessário verificar se o grupo existe.</span><span class="sxs-lookup"><span data-stu-id="ae6a6-127">Determines whether to check if the group exists.</span></span> <span data-ttu-id="ae6a6-128">Defina essa propriedade como **Present** para garantir que o grupo exista.</span><span class="sxs-lookup"><span data-stu-id="ae6a6-128">Set this property to **Present** to ensure the group exists.</span></span> <span data-ttu-id="ae6a6-129">Defina-a como **Absent** para garantir que o grupo não exista.</span><span class="sxs-lookup"><span data-stu-id="ae6a6-129">Set it to **Absent** to ensure the group does not exist.</span></span> <span data-ttu-id="ae6a6-130">O valor padrão é **Present**.</span><span class="sxs-lookup"><span data-stu-id="ae6a6-130">The default value is **Present**.</span></span> |

## <a name="example"></a><span data-ttu-id="ae6a6-131">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ae6a6-131">Example</span></span>

<span data-ttu-id="ae6a6-132">O exemplo a seguir garante que o usuário 'monuser' exista e seja membro do grupo 'DBusers'.</span><span class="sxs-lookup"><span data-stu-id="ae6a6-132">The following example ensures that the user 'monuser' exists and is a member of the group 'DBusers'.</span></span>

```powershell
Import-DSCResource -Module nx

Node $node
{
    nxUser UserExample {
       UserName = 'monuser'
       Description = 'Monitoring user'
       Password = '$6$fZAne/Qc$MZejMrOxDK0ogv9SLiBP5J5qZFBvXLnDu8HY1Oy7ycX.Y3C7mGPUfeQy3A82ev3zIabhDQnj2ayeuGn02CqE/0'
       Ensure = 'Present'
       HomeDirectory = '/home/monuser'
    }

    nxGroup GroupExample {
       GroupName = 'DBusers'
       Ensure = 'Present'
       MembersToInclude = 'monuser'
       DependsOn = '[nxUser]UserExample'
    }
}
```
