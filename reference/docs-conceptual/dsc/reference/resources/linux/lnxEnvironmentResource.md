---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso nxEnvironment de DSC para Linux
ms.openlocfilehash: 64de54fbde15f9d4d7fac425af27b6ef11347dce
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560888"
---
# <a name="dsc-for-linux-nxenvironment-resource"></a><span data-ttu-id="7c65a-103">Recurso nxEnvironment de DSC para Linux</span><span class="sxs-lookup"><span data-stu-id="7c65a-103">DSC for Linux nxEnvironment Resource</span></span>

<span data-ttu-id="7c65a-104">O recurso **nxEnvironment** na Configuração de Estado Desejado (DSC) do PowerShell fornece um mecanismo para gerenciar as variáveis de ambiente do sistema em um nó do Linux.</span><span class="sxs-lookup"><span data-stu-id="7c65a-104">The **nxEnvironment** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage system environment variables on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="7c65a-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7c65a-105">Syntax</span></span>

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

## <a name="properties"></a><span data-ttu-id="7c65a-106">Propriedades</span><span class="sxs-lookup"><span data-stu-id="7c65a-106">Properties</span></span>

|<span data-ttu-id="7c65a-107">Propriedade</span><span class="sxs-lookup"><span data-stu-id="7c65a-107">Property</span></span> |<span data-ttu-id="7c65a-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="7c65a-108">Description</span></span> |
|---|---|
|<span data-ttu-id="7c65a-109">Nome</span><span class="sxs-lookup"><span data-stu-id="7c65a-109">Name</span></span> |<span data-ttu-id="7c65a-110">Indica o nome da variável de ambiente para a qual você deseja garantir um estado específico.</span><span class="sxs-lookup"><span data-stu-id="7c65a-110">Indicates the name of the environment variable for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="7c65a-111">Valor</span><span class="sxs-lookup"><span data-stu-id="7c65a-111">Value</span></span> |<span data-ttu-id="7c65a-112">O valor que será atribuído à variável de ambiente.</span><span class="sxs-lookup"><span data-stu-id="7c65a-112">The value to assign to the environment variable.</span></span> |
|<span data-ttu-id="7c65a-113">Caminho</span><span class="sxs-lookup"><span data-stu-id="7c65a-113">Path</span></span> |<span data-ttu-id="7c65a-114">Define a variável de ambiente que está sendo configurada.</span><span class="sxs-lookup"><span data-stu-id="7c65a-114">Defines the environment variable that is being configured.</span></span> <span data-ttu-id="7c65a-115">Defina essa propriedade como `$true` se a variável for **Path**. Caso contrário, defina-a como `$false`.</span><span class="sxs-lookup"><span data-stu-id="7c65a-115">Set this property to `$true` if the variable is the **Path** variable; otherwise, set it to `$false`.</span></span> <span data-ttu-id="7c65a-116">O padrão é `$false`.</span><span class="sxs-lookup"><span data-stu-id="7c65a-116">The default is `$false`.</span></span> <span data-ttu-id="7c65a-117">Se a variável que estiver sendo configurada for a variável **Path**, o valor fornecido por meio da propriedade **Value** será acrescentado ao valor existente.</span><span class="sxs-lookup"><span data-stu-id="7c65a-117">If the variable being configured is the **Path** variable, the value provided through the **Value** property will be appended to the existing value.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="7c65a-118">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="7c65a-118">Common properties</span></span>

|<span data-ttu-id="7c65a-119">Propriedade</span><span class="sxs-lookup"><span data-stu-id="7c65a-119">Property</span></span> |<span data-ttu-id="7c65a-120">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="7c65a-120">Description</span></span> |
|---|---|
|<span data-ttu-id="7c65a-121">DependsOn</span><span class="sxs-lookup"><span data-stu-id="7c65a-121">DependsOn</span></span> |<span data-ttu-id="7c65a-122">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="7c65a-122">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="7c65a-123">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="7c65a-123">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="7c65a-124">Ensure</span><span class="sxs-lookup"><span data-stu-id="7c65a-124">Ensure</span></span> |<span data-ttu-id="7c65a-125">Determina se é necessário verificar se a variável existe.</span><span class="sxs-lookup"><span data-stu-id="7c65a-125">Determines whether to check if the variable exists.</span></span> <span data-ttu-id="7c65a-126">Defina essa propriedade como **Present** para garantir que a variável exista.</span><span class="sxs-lookup"><span data-stu-id="7c65a-126">Set this property to **Present** to ensure the variable exists.</span></span> <span data-ttu-id="7c65a-127">Defina-a como **Absent** para garantir que a variável não exista.</span><span class="sxs-lookup"><span data-stu-id="7c65a-127">Set it to **Absent** to ensure the variable does not exist.</span></span> <span data-ttu-id="7c65a-128">O valor padrão é **Present**.</span><span class="sxs-lookup"><span data-stu-id="7c65a-128">The default value is **Present**.</span></span> |

## <a name="additional-information"></a><span data-ttu-id="7c65a-129">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="7c65a-129">Additional Information</span></span>

- <span data-ttu-id="7c65a-130">Se **Path** estiver ausente ou definido como `$false`, as variáveis de ambiente serão gerenciadas em `/etc/environment`.</span><span class="sxs-lookup"><span data-stu-id="7c65a-130">If **Path** is absent or set to `$false`, environment variables are managed in `/etc/environment`.</span></span>
  <span data-ttu-id="7c65a-131">Seus programas ou scripts poderão exigir uma configuração para fornecer o arquivo `/etc/environment` para acessar as variáveis de ambiente gerenciadas.</span><span class="sxs-lookup"><span data-stu-id="7c65a-131">Your programs or scripts may require configuration to source the `/etc/environment` file to access the managed environment variables.</span></span>
- <span data-ttu-id="7c65a-132">Se **Path** estiver definido como `$true`, a variável de ambiente será gerenciada no arquivo `/etc/profile.d/DSCenvironment.sh`.</span><span class="sxs-lookup"><span data-stu-id="7c65a-132">If **Path** is set to `$true`, the environment variable is managed in the file `/etc/profile.d/DSCenvironment.sh`.</span></span> <span data-ttu-id="7c65a-133">Esse arquivo será criado se não existir.</span><span class="sxs-lookup"><span data-stu-id="7c65a-133">This file will be created if it does not exist.</span></span> <span data-ttu-id="7c65a-134">Se **Ensure** estiver definido como **Absent** e **Path** estiver definido como `$true`, uma variável de ambiente existente será removida somente de `/etc/profile.d/DSCenvironment.sh`, e não de outros arquivos.</span><span class="sxs-lookup"><span data-stu-id="7c65a-134">If **Ensure** is set to **Absent** and **Path** is set to `$true`, an existing environment variable will only be removed from `/etc/profile.d/DSCenvironment.sh` and not from other files.</span></span>

## <a name="example"></a><span data-ttu-id="7c65a-135">Exemplo</span><span class="sxs-lookup"><span data-stu-id="7c65a-135">Example</span></span>

<span data-ttu-id="7c65a-136">O exemplo a seguir mostra como usar o recurso **nxEnvironment** para garantir que **TestEnvironmentVariable** esteja presente e tenha o valor "Test-Value".</span><span class="sxs-lookup"><span data-stu-id="7c65a-136">The following example shows how to use the **nxEnvironment** resource to ensure that **TestEnvironmentVariable** is present and has the value "Test-Value".</span></span> <span data-ttu-id="7c65a-137">Se **TestEnvironmentVariable** não estiver presente, será criado.</span><span class="sxs-lookup"><span data-stu-id="7c65a-137">If **TestEnvironmentVariable** is not present, it will be created.</span></span>

```powershell
Import-DSCResource -Module nx

nxEnvironment EnvironmentExample
{
    Ensure = "Present"
    Name = "TestEnvironmentVariable"
    Value = "TestValue"
}
```
