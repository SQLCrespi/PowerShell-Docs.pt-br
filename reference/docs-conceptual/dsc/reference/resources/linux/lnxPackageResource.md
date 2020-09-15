---
ms.date: 07/17/2020
keywords: DSC,powershell,configuração,instalação
title: Recurso nxPackage de DSC para Linux
ms.openlocfilehash: f61b337f6fbb8e2ea48128642874f050787fc576
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464478"
---
# <a name="dsc-for-linux-nxpackage-resource"></a><span data-ttu-id="57486-103">Recurso nxPackage de DSC para Linux</span><span class="sxs-lookup"><span data-stu-id="57486-103">DSC for Linux nxPackage Resource</span></span>

<span data-ttu-id="57486-104">O recurso **nxPackage** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para gerenciar pacotes em um nó do Linux.</span><span class="sxs-lookup"><span data-stu-id="57486-104">The **nxPackage** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage packages on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="57486-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="57486-105">Syntax</span></span>

```Syntax
nxPackage <string> #ResourceName
{
    Name = <string>
    [ PackageManager = <string> { Yum | Apt | Zypper } ]
    [ PackageGroup = <bool>]
    [ Arguments = <string> ]
    [ ReturnCode = <uint32> ]
    [ FilePath = <string> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present }  ]
}
```

## <a name="properties"></a><span data-ttu-id="57486-106">Propriedades</span><span class="sxs-lookup"><span data-stu-id="57486-106">Properties</span></span>

|<span data-ttu-id="57486-107">Propriedade</span><span class="sxs-lookup"><span data-stu-id="57486-107">Property</span></span> |<span data-ttu-id="57486-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="57486-108">Description</span></span> |
|---|---|
|<span data-ttu-id="57486-109">Nome</span><span class="sxs-lookup"><span data-stu-id="57486-109">Name</span></span> |<span data-ttu-id="57486-110">O nome do pacote para o qual você deseja garantir um estado específico.</span><span class="sxs-lookup"><span data-stu-id="57486-110">The name of the package for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="57486-111">PackageManager</span><span class="sxs-lookup"><span data-stu-id="57486-111">PackageManager</span></span> |<span data-ttu-id="57486-112">Os valores compatíveis são **yum**, **apt** e **zypper**.</span><span class="sxs-lookup"><span data-stu-id="57486-112">Supported values are **yum**, **apt**, and **zypper**.</span></span> <span data-ttu-id="57486-113">Especifica o gerenciador de pacotes que deve ser usado ao instalar pacotes.</span><span class="sxs-lookup"><span data-stu-id="57486-113">Specifies the package manager to use when installing packages.</span></span> <span data-ttu-id="57486-114">Se **FilePath** for especificado, o caminho fornecido será usado para instalar o pacote.</span><span class="sxs-lookup"><span data-stu-id="57486-114">If **FilePath** is specified, the provided path will be used to install the package.</span></span> <span data-ttu-id="57486-115">Caso contrário, será usado um Gerenciador de Pacotes para instalar o pacote por meio de um repositório pré-configurado.</span><span class="sxs-lookup"><span data-stu-id="57486-115">Otherwise, a Package Manager will be used to install the package from a pre-configured repository.</span></span> <span data-ttu-id="57486-116">Se não for fornecido o **PackageManager** ou o **FilePath**, o gerenciador de pacotes padrão para o sistema será usado.</span><span class="sxs-lookup"><span data-stu-id="57486-116">If neither **PackageManager** nor **FilePath** are provided, the default package manager for the system will be used.</span></span> |
|<span data-ttu-id="57486-117">PackageGroup</span><span class="sxs-lookup"><span data-stu-id="57486-117">PackageGroup</span></span> |<span data-ttu-id="57486-118">Se for `$true`, o **Name** deverá ser o nome de um grupo de pacotes para usar com um **PackageManager**.</span><span class="sxs-lookup"><span data-stu-id="57486-118">If `$true`, the **Name** is expected to be the name of a package group for use with a **PackageManager**.</span></span> <span data-ttu-id="57486-119">**PackageGroup** não é válido quando fornece um **FilePath**.</span><span class="sxs-lookup"><span data-stu-id="57486-119">**PackageGroup** is not valid when providing a **FilePath**.</span></span> |
|<span data-ttu-id="57486-120">Argumentos</span><span class="sxs-lookup"><span data-stu-id="57486-120">Arguments</span></span> |<span data-ttu-id="57486-121">Uma cadeia de caracteres de argumentos que será passada para o pacote exatamente conforme fornecido.</span><span class="sxs-lookup"><span data-stu-id="57486-121">A string of arguments that will be passed to the package exactly as provided.</span></span> |
|<span data-ttu-id="57486-122">ReturnCode</span><span class="sxs-lookup"><span data-stu-id="57486-122">ReturnCode</span></span> |<span data-ttu-id="57486-123">O código de retorno esperado.</span><span class="sxs-lookup"><span data-stu-id="57486-123">The expected return code.</span></span> <span data-ttu-id="57486-124">Se o código de retorno real não corresponder ao valor esperado fornecido aqui, a configuração gerará um erro.</span><span class="sxs-lookup"><span data-stu-id="57486-124">If the actual return code does not match the expected value provided here, the configuration will return an error.</span></span> |
|<span data-ttu-id="57486-125">FilePath</span><span class="sxs-lookup"><span data-stu-id="57486-125">FilePath</span></span> |<span data-ttu-id="57486-126">O caminho do arquivo em que o pacote reside.</span><span class="sxs-lookup"><span data-stu-id="57486-126">The file path where the package resides.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="57486-127">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="57486-127">Common properties</span></span>

|<span data-ttu-id="57486-128">Propriedade</span><span class="sxs-lookup"><span data-stu-id="57486-128">Property</span></span> |<span data-ttu-id="57486-129">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="57486-129">Description</span></span> |
|---|---|
|<span data-ttu-id="57486-130">DependsOn</span><span class="sxs-lookup"><span data-stu-id="57486-130">DependsOn</span></span> |<span data-ttu-id="57486-131">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="57486-131">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="57486-132">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="57486-132">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="57486-133">Ensure</span><span class="sxs-lookup"><span data-stu-id="57486-133">Ensure</span></span> |<span data-ttu-id="57486-134">Determina se é necessário verificar se o pacote existe.</span><span class="sxs-lookup"><span data-stu-id="57486-134">Determines whether to check if the package exists.</span></span> <span data-ttu-id="57486-135">Defina essa propriedade como **Present** para garantir que o pacote exista.</span><span class="sxs-lookup"><span data-stu-id="57486-135">Set this property to **Present** to ensure the package exists.</span></span> <span data-ttu-id="57486-136">Defina-a como **Absent** para garantir que o pacote não exista.</span><span class="sxs-lookup"><span data-stu-id="57486-136">Set it to **Absent** to ensure the package does not exist.</span></span> <span data-ttu-id="57486-137">O valor padrão é **Present**.</span><span class="sxs-lookup"><span data-stu-id="57486-137">The default value is **Present**.</span></span> |

## <a name="example"></a><span data-ttu-id="57486-138">Exemplo</span><span class="sxs-lookup"><span data-stu-id="57486-138">Example</span></span>

<span data-ttu-id="57486-139">O exemplo a seguir assegura que o pacote denominado "httpd" seja instalado em um computador Linux usando o gerenciador de pacotes "Yum".</span><span class="sxs-lookup"><span data-stu-id="57486-139">The following example ensures that the package named "httpd" is installed on a Linux computer, using the "Yum" package manager.</span></span>

```powershell
Import-DSCResource -Module nx

Node $node
{
    nxPackage httpd
    {
        Name = "httpd"
        Ensure = "Present"
        PackageManager = "Yum"
    }
}
```
