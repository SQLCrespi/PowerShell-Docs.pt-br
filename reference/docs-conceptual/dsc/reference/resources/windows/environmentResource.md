---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso Environment de DSC
ms.openlocfilehash: d6d3b4a2086be28fbfa2bf200acef9b13b7b7825
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "71954713"
---
# <a name="dsc-environment-resource"></a><span data-ttu-id="65ad4-103">Recurso Environment de DSC</span><span class="sxs-lookup"><span data-stu-id="65ad4-103">DSC Environment Resource</span></span>

> <span data-ttu-id="65ad4-104">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="65ad4-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="65ad4-105">O recurso **Environment** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para gerenciar as variáveis de ambiente do sistema.</span><span class="sxs-lookup"><span data-stu-id="65ad4-105">The **Environment** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage system environment variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="65ad4-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="65ad4-106">Syntax</span></span>

```Syntax
Environment [string] #ResourceName
{
    Name = [string]
    [ Path = [bool] ]
    [ Value = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="65ad4-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="65ad4-107">Properties</span></span>

|<span data-ttu-id="65ad4-108">Propriedade</span><span class="sxs-lookup"><span data-stu-id="65ad4-108">Property</span></span> |<span data-ttu-id="65ad4-109">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="65ad4-109">Description</span></span> |
|---|---|
|<span data-ttu-id="65ad4-110">Nome</span><span class="sxs-lookup"><span data-stu-id="65ad4-110">Name</span></span> |<span data-ttu-id="65ad4-111">Indica o nome da variável de ambiente para a qual você deseja garantir um estado específico.</span><span class="sxs-lookup"><span data-stu-id="65ad4-111">Indicates the name of the environment variable for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="65ad4-112">Caminho</span><span class="sxs-lookup"><span data-stu-id="65ad4-112">Path</span></span> |<span data-ttu-id="65ad4-113">Define a variável de ambiente que está sendo configurada.</span><span class="sxs-lookup"><span data-stu-id="65ad4-113">Defines the environment variable that is being configured.</span></span> <span data-ttu-id="65ad4-114">Defina essa propriedade como `$true` se a variável for **Path**. Caso contrário, defina-a como `$false`.</span><span class="sxs-lookup"><span data-stu-id="65ad4-114">Set this property to `$true` if the variable is the **Path** variable; otherwise, set it to `$false`.</span></span> <span data-ttu-id="65ad4-115">O padrão é `$false`.</span><span class="sxs-lookup"><span data-stu-id="65ad4-115">The default is `$false`.</span></span> <span data-ttu-id="65ad4-116">Se a variável que estiver sendo configurada for a variável **Path**, o valor fornecido por meio da propriedade **Value** será acrescentado ao valor existente.</span><span class="sxs-lookup"><span data-stu-id="65ad4-116">If the variable being configured is the **Path** variable, the value provided through the **Value** property will be appended to the existing value.</span></span> |
|<span data-ttu-id="65ad4-117">Valor</span><span class="sxs-lookup"><span data-stu-id="65ad4-117">Value</span></span> |<span data-ttu-id="65ad4-118">O valor que será atribuído à variável de ambiente.</span><span class="sxs-lookup"><span data-stu-id="65ad4-118">The value to assign to the environment variable.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="65ad4-119">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="65ad4-119">Common properties</span></span>

|<span data-ttu-id="65ad4-120">Propriedade</span><span class="sxs-lookup"><span data-stu-id="65ad4-120">Property</span></span> |<span data-ttu-id="65ad4-121">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="65ad4-121">Description</span></span> |
|---|---|
|<span data-ttu-id="65ad4-122">DependsOn</span><span class="sxs-lookup"><span data-stu-id="65ad4-122">DependsOn</span></span> |<span data-ttu-id="65ad4-123">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="65ad4-123">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="65ad4-124">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="65ad4-124">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="65ad4-125">Ensure</span><span class="sxs-lookup"><span data-stu-id="65ad4-125">Ensure</span></span> |<span data-ttu-id="65ad4-126">Indica se existe uma variável.</span><span class="sxs-lookup"><span data-stu-id="65ad4-126">Indicates if a variable exists.</span></span> <span data-ttu-id="65ad4-127">Defina essa propriedade como **Present** para criar a variável de ambiente caso ela não exista ou para garantir que seu valor corresponda ao que é fornecido por meio da propriedade **Value** se a variável já existir.</span><span class="sxs-lookup"><span data-stu-id="65ad4-127">Set this property to **Present** to create the environment variable if it does not exist or to ensure that its value matches what is provided through the **Value** property if the variable already exists.</span></span> <span data-ttu-id="65ad4-128">Defina-a como **Absent** para excluir a variável se ela existir.</span><span class="sxs-lookup"><span data-stu-id="65ad4-128">Set it to **Absent** to delete the variable if it exists.</span></span> |
|<span data-ttu-id="65ad4-129">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="65ad4-129">PsDscRunAsCredential</span></span> |<span data-ttu-id="65ad4-130">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="65ad4-130">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="65ad4-131">A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais.</span><span class="sxs-lookup"><span data-stu-id="65ad4-131">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="65ad4-132">Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="65ad4-132">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="65ad4-133">Exemplo</span><span class="sxs-lookup"><span data-stu-id="65ad4-133">Example</span></span>

<span data-ttu-id="65ad4-134">O exemplo a seguir assegura que TestEnvironmentVariable esteja presente e tenha o valor _TestValue_.</span><span class="sxs-lookup"><span data-stu-id="65ad4-134">The following example ensures that TestEnvironmentVariable is present and it has the value _TestValue_.</span></span> <span data-ttu-id="65ad4-135">Se não estiver presente, será criado.</span><span class="sxs-lookup"><span data-stu-id="65ad4-135">If it is not present, it creates it.</span></span>

```powershell
Environment EnvironmentExample
{
    Ensure = "Present"  # You can also set Ensure to "Absent"
    Name = "TestEnvironmentVariable"
    Value = "TestValue"
}
```