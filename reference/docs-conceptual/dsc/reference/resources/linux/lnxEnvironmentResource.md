---
ms.date: 07/17/2020
ms.topic: reference
title: Recurso nxEnvironment de DSC para Linux
description: Recurso nxEnvironment de DSC para Linux
ms.openlocfilehash: 86ed538732254967cb4a3bb55af4f6b179947e52
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644677"
---
# <a name="dsc-for-linux-nxenvironment-resource"></a><span data-ttu-id="93996-103">Recurso nxEnvironment de DSC para Linux</span><span class="sxs-lookup"><span data-stu-id="93996-103">DSC for Linux nxEnvironment Resource</span></span>

<span data-ttu-id="93996-104">O recurso **nxEnvironment** na Configuração de Estado Desejado (DSC) do PowerShell fornece um mecanismo para gerenciar as variáveis de ambiente do sistema em um nó do Linux.</span><span class="sxs-lookup"><span data-stu-id="93996-104">The **nxEnvironment** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage system environment variables on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="93996-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="93996-105">Syntax</span></span>

```Syntax
nxEnvironment <string> #ResourceName
{
    Name = <string>
    [ Value = <string>
    [ Path = <bool> }
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present }  ]
}
```

## <a name="properties"></a><span data-ttu-id="93996-106">Propriedades</span><span class="sxs-lookup"><span data-stu-id="93996-106">Properties</span></span>

|<span data-ttu-id="93996-107">Propriedade</span><span class="sxs-lookup"><span data-stu-id="93996-107">Property</span></span> |<span data-ttu-id="93996-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="93996-108">Description</span></span> |
|---|---|
|<span data-ttu-id="93996-109">Nome</span><span class="sxs-lookup"><span data-stu-id="93996-109">Name</span></span> |<span data-ttu-id="93996-110">Indica o nome da variável de ambiente para a qual você deseja garantir um estado específico.</span><span class="sxs-lookup"><span data-stu-id="93996-110">Indicates the name of the environment variable for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="93996-111">Valor</span><span class="sxs-lookup"><span data-stu-id="93996-111">Value</span></span> |<span data-ttu-id="93996-112">O valor que será atribuído à variável de ambiente.</span><span class="sxs-lookup"><span data-stu-id="93996-112">The value to assign to the environment variable.</span></span> |
|<span data-ttu-id="93996-113">Caminho</span><span class="sxs-lookup"><span data-stu-id="93996-113">Path</span></span> |<span data-ttu-id="93996-114">Define a variável de ambiente que está sendo configurada.</span><span class="sxs-lookup"><span data-stu-id="93996-114">Defines the environment variable that is being configured.</span></span> <span data-ttu-id="93996-115">Defina essa propriedade como `$true` se a variável for **Path** . Caso contrário, defina-a como `$false`.</span><span class="sxs-lookup"><span data-stu-id="93996-115">Set this property to `$true` if the variable is the **Path** variable; otherwise, set it to `$false`.</span></span> <span data-ttu-id="93996-116">O padrão é `$false`.</span><span class="sxs-lookup"><span data-stu-id="93996-116">The default is `$false`.</span></span> <span data-ttu-id="93996-117">Se a variável que estiver sendo configurada for a variável **Path** , o valor fornecido por meio da propriedade **Value** será acrescentado ao valor existente.</span><span class="sxs-lookup"><span data-stu-id="93996-117">If the variable being configured is the **Path** variable, the value provided through the **Value** property will be appended to the existing value.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="93996-118">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="93996-118">Common properties</span></span>

|<span data-ttu-id="93996-119">Propriedade</span><span class="sxs-lookup"><span data-stu-id="93996-119">Property</span></span> |<span data-ttu-id="93996-120">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="93996-120">Description</span></span> |
|---|---|
|<span data-ttu-id="93996-121">DependsOn</span><span class="sxs-lookup"><span data-stu-id="93996-121">DependsOn</span></span> |<span data-ttu-id="93996-122">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="93996-122">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="93996-123">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="93996-123">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="93996-124">Ensure</span><span class="sxs-lookup"><span data-stu-id="93996-124">Ensure</span></span> |<span data-ttu-id="93996-125">Determina se é necessário verificar se a variável existe.</span><span class="sxs-lookup"><span data-stu-id="93996-125">Determines whether to check if the variable exists.</span></span> <span data-ttu-id="93996-126">Defina essa propriedade como **Present** para garantir que a variável exista.</span><span class="sxs-lookup"><span data-stu-id="93996-126">Set this property to **Present** to ensure the variable exists.</span></span> <span data-ttu-id="93996-127">Defina-a como **Absent** para garantir que a variável não exista.</span><span class="sxs-lookup"><span data-stu-id="93996-127">Set it to **Absent** to ensure the variable does not exist.</span></span> <span data-ttu-id="93996-128">O valor padrão é **Present** .</span><span class="sxs-lookup"><span data-stu-id="93996-128">The default value is **Present** .</span></span> |

## <a name="additional-information"></a><span data-ttu-id="93996-129">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="93996-129">Additional Information</span></span>

- <span data-ttu-id="93996-130">Se **Path** estiver ausente ou definido como `$false`, as variáveis de ambiente serão gerenciadas em `/etc/environment`.</span><span class="sxs-lookup"><span data-stu-id="93996-130">If **Path** is absent or set to `$false`, environment variables are managed in `/etc/environment`.</span></span>
  <span data-ttu-id="93996-131">Seus programas ou scripts poderão exigir uma configuração para fornecer o arquivo `/etc/environment` para acessar as variáveis de ambiente gerenciadas.</span><span class="sxs-lookup"><span data-stu-id="93996-131">Your programs or scripts may require configuration to source the `/etc/environment` file to access the managed environment variables.</span></span>
- <span data-ttu-id="93996-132">Se **Path** estiver definido como `$true`, a variável de ambiente será gerenciada no arquivo `/etc/profile.d/DSCenvironment.sh`.</span><span class="sxs-lookup"><span data-stu-id="93996-132">If **Path** is set to `$true`, the environment variable is managed in the file `/etc/profile.d/DSCenvironment.sh`.</span></span> <span data-ttu-id="93996-133">Esse arquivo será criado se não existir.</span><span class="sxs-lookup"><span data-stu-id="93996-133">This file will be created if it does not exist.</span></span> <span data-ttu-id="93996-134">Se **Ensure** estiver definido como **Absent** e **Path** estiver definido como `$true`, uma variável de ambiente existente será removida somente de `/etc/profile.d/DSCenvironment.sh`, e não de outros arquivos.</span><span class="sxs-lookup"><span data-stu-id="93996-134">If **Ensure** is set to **Absent** and **Path** is set to `$true`, an existing environment variable will only be removed from `/etc/profile.d/DSCenvironment.sh` and not from other files.</span></span>

## <a name="example"></a><span data-ttu-id="93996-135">Exemplo</span><span class="sxs-lookup"><span data-stu-id="93996-135">Example</span></span>

<span data-ttu-id="93996-136">O exemplo a seguir mostra como usar o recurso **nxEnvironment** para garantir que **TestEnvironmentVariable** esteja presente e tenha o valor "Test-Value".</span><span class="sxs-lookup"><span data-stu-id="93996-136">The following example shows how to use the **nxEnvironment** resource to ensure that **TestEnvironmentVariable** is present and has the value "Test-Value".</span></span> <span data-ttu-id="93996-137">Se **TestEnvironmentVariable** não estiver presente, será criado.</span><span class="sxs-lookup"><span data-stu-id="93996-137">If **TestEnvironmentVariable** is not present, it will be created.</span></span>

```powershell
Import-DSCResource -Module nx

nxEnvironment EnvironmentExample
{
    Ensure = "Present"
    Name = "TestEnvironmentVariable"
    Value = "TestValue"
}
```
