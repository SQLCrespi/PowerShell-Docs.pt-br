---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso Package de DSC
ms.openlocfilehash: ff2eae712b4117da9bca915f52e18caed7c4885d
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83559923"
---
# <a name="dsc-package-resource"></a><span data-ttu-id="4dd1d-103">Recurso Package de DSC</span><span class="sxs-lookup"><span data-stu-id="4dd1d-103">DSC Package Resource</span></span>

> <span data-ttu-id="4dd1d-104">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="4dd1d-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="4dd1d-105">O recurso **Package** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para instalar ou desinstalar pacotes, tais como os pacotes do Windows Installer e setup.exe, em um nó de destino.</span><span class="sxs-lookup"><span data-stu-id="4dd1d-105">The **Package** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to install or uninstall packages, such as Windows Installer and setup.exe packages, on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="4dd1d-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4dd1d-106">Syntax</span></span>

```Syntax
Package [string] #ResourceName
{
    Name = [string]
    Path = [string]
    ProductId = [string]
    [ Arguments = [string] ]
    [ Credential = [PSCredential] ]
    [ LogPath = [string] ]
    [ ReturnCode = [UInt32[]] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="4dd1d-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="4dd1d-107">Properties</span></span>

|<span data-ttu-id="4dd1d-108">Propriedade</span><span class="sxs-lookup"><span data-stu-id="4dd1d-108">Property</span></span> |<span data-ttu-id="4dd1d-109">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="4dd1d-109">Description</span></span> |
|---|---|
|<span data-ttu-id="4dd1d-110">Nome</span><span class="sxs-lookup"><span data-stu-id="4dd1d-110">Name</span></span> |<span data-ttu-id="4dd1d-111">Indica o nome do pacote para o qual você deseja garantir um estado específico.</span><span class="sxs-lookup"><span data-stu-id="4dd1d-111">Indicates the name of the package for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="4dd1d-112">Caminho</span><span class="sxs-lookup"><span data-stu-id="4dd1d-112">Path</span></span> |<span data-ttu-id="4dd1d-113">Indica o caminho em que o pacote reside.</span><span class="sxs-lookup"><span data-stu-id="4dd1d-113">Indicates the path where the package resides.</span></span> |
|<span data-ttu-id="4dd1d-114">ProductId</span><span class="sxs-lookup"><span data-stu-id="4dd1d-114">ProductId</span></span> |<span data-ttu-id="4dd1d-115">Indica a ID do produto que identifica o pacote com exclusividade.</span><span class="sxs-lookup"><span data-stu-id="4dd1d-115">Indicates the product ID that uniquely identifies the package.</span></span> |
|<span data-ttu-id="4dd1d-116">Argumentos</span><span class="sxs-lookup"><span data-stu-id="4dd1d-116">Arguments</span></span> |<span data-ttu-id="4dd1d-117">Lista uma cadeia de caracteres de argumentos que será passada para o pacote exatamente conforme fornecido.</span><span class="sxs-lookup"><span data-stu-id="4dd1d-117">Lists a string of arguments that will be passed to the package exactly as provided.</span></span> |
|<span data-ttu-id="4dd1d-118">Credencial</span><span class="sxs-lookup"><span data-stu-id="4dd1d-118">Credential</span></span> |<span data-ttu-id="4dd1d-119">Fornece acesso ao pacote em uma fonte remota.</span><span class="sxs-lookup"><span data-stu-id="4dd1d-119">Provides access to the package on a remote source.</span></span> <span data-ttu-id="4dd1d-120">Essa propriedade não é usada para instalar o pacote.</span><span class="sxs-lookup"><span data-stu-id="4dd1d-120">This property is not used to install the package.</span></span> <span data-ttu-id="4dd1d-121">O pacote é sempre instalado no sistema local.</span><span class="sxs-lookup"><span data-stu-id="4dd1d-121">The package is always installed on the local system.</span></span> |
|<span data-ttu-id="4dd1d-122">LogPath</span><span class="sxs-lookup"><span data-stu-id="4dd1d-122">LogPath</span></span> |<span data-ttu-id="4dd1d-123">Indica o caminho completo em que você deseja que o provedor salve um arquivo de log para instalar ou desinstalar o pacote.</span><span class="sxs-lookup"><span data-stu-id="4dd1d-123">Indicates the full path where you want the provider to save a log file to install or uninstall the package.</span></span> |
|<span data-ttu-id="4dd1d-124">ReturnCode</span><span class="sxs-lookup"><span data-stu-id="4dd1d-124">ReturnCode</span></span> |<span data-ttu-id="4dd1d-125">Indica o código de retorno esperado.</span><span class="sxs-lookup"><span data-stu-id="4dd1d-125">Indicates the expected return code.</span></span> <span data-ttu-id="4dd1d-126">Se o código de retorno real não corresponder ao valor esperado fornecido aqui, a configuração gerará um erro.</span><span class="sxs-lookup"><span data-stu-id="4dd1d-126">If the actual return code does not match the expected value provided here, the configuration will return an error.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="4dd1d-127">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="4dd1d-127">Common properties</span></span>

|<span data-ttu-id="4dd1d-128">Propriedade</span><span class="sxs-lookup"><span data-stu-id="4dd1d-128">Property</span></span> |<span data-ttu-id="4dd1d-129">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="4dd1d-129">Description</span></span> |
|---|---|
|<span data-ttu-id="4dd1d-130">DependsOn</span><span class="sxs-lookup"><span data-stu-id="4dd1d-130">DependsOn</span></span> |<span data-ttu-id="4dd1d-131">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="4dd1d-131">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="4dd1d-132">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="4dd1d-132">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="4dd1d-133">Ensure</span><span class="sxs-lookup"><span data-stu-id="4dd1d-133">Ensure</span></span> |<span data-ttu-id="4dd1d-134">Indica se o pacote foi instalado.</span><span class="sxs-lookup"><span data-stu-id="4dd1d-134">Indicates if the package is installed.</span></span> <span data-ttu-id="4dd1d-135">Defina esta propriedade como **Absent** para garantir que o pacote não seja instalado (ou desinstalar o pacote, se ele estiver instalado).</span><span class="sxs-lookup"><span data-stu-id="4dd1d-135">Set this property to **Absent** to ensure the package is not installed (or uninstall the package if it is installed).</span></span> <span data-ttu-id="4dd1d-136">Defina-a como **Present** para garantir que o pacote seja instalado.</span><span class="sxs-lookup"><span data-stu-id="4dd1d-136">Set it to **Present** to ensure the package is installed.</span></span> <span data-ttu-id="4dd1d-137">O valor padrão é **Present**.</span><span class="sxs-lookup"><span data-stu-id="4dd1d-137">The default value is **Present**.</span></span> |
|<span data-ttu-id="4dd1d-138">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="4dd1d-138">PsDscRunAsCredential</span></span> |<span data-ttu-id="4dd1d-139">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="4dd1d-139">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="4dd1d-140">A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais.</span><span class="sxs-lookup"><span data-stu-id="4dd1d-140">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="4dd1d-141">Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="4dd1d-141">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="4dd1d-142">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4dd1d-142">Example</span></span>

<span data-ttu-id="4dd1d-143">Este exemplo executa o instalador .msi que está localizado no caminho especificado e tem a ID do produto especificado.</span><span class="sxs-lookup"><span data-stu-id="4dd1d-143">This example runs the .msi installer that is located at the specified path and has the specified product ID.</span></span>

```powershell
Configuration PackageTest
{
    Package PackageExample
    {
        Ensure      = "Present"  # You can also set Ensure to "Absent"
        Path        = "$Env:SystemDrive\TestFolder\TestProject.msi"
        Name        = "TestPackage"
        ProductId   = "ACDDCDAF-80C6-41E6-A1B9-8ABD8A05027E"
    }
}
```
