---
ms.date: 07/16/2020
ms.topic: reference
title: Recurso de DSC WindowsPackageCab
description: Recurso de DSC WindowsPackageCab
ms.openlocfilehash: 3ac10eb2a7da502b8cac23ab8bfee869a4e26fd3
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2020
ms.locfileid: "93143017"
---
# <a name="dsc-windowspackagecab-resource"></a><span data-ttu-id="63581-103">Recurso de DSC WindowsPackageCab</span><span class="sxs-lookup"><span data-stu-id="63581-103">DSC WindowsPackageCab Resource</span></span>

> <span data-ttu-id="63581-104">Aplica-se a: Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="63581-104">Applies To: Windows PowerShell 5.1</span></span>

<span data-ttu-id="63581-105">O **WindowsPackageCab** no DSC (Desired State Configuration) do Windows PowerShell fornece um mecanismo para instalar ou desinstalar pacotes de gabinete (.cab) do Windows em um nó de destino.</span><span class="sxs-lookup"><span data-stu-id="63581-105">The **WindowsPackageCab** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to install or uninstall Windows cabinet (.cab) packages on a target node.</span></span>

<span data-ttu-id="63581-106">O nó de destino deve ter o módulo PowerShell do DISM instalado.</span><span class="sxs-lookup"><span data-stu-id="63581-106">The target node must have the DISM PowerShell module installed.</span></span> <span data-ttu-id="63581-107">Para obter informações, consulte [Usar DISM no Windows PowerShell](/windows-hardware/manufacture/desktop/use-dism-in-windows-powershell-s14).</span><span class="sxs-lookup"><span data-stu-id="63581-107">For information, see [Use DISM in Windows PowerShell](/windows-hardware/manufacture/desktop/use-dism-in-windows-powershell-s14).</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a><span data-ttu-id="63581-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="63581-108">Syntax</span></span>

```Syntax
{
    Name = [string]
    SourcePath = [string]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    Ensure = [string] { Absent | Present }
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="63581-109">Propriedades</span><span class="sxs-lookup"><span data-stu-id="63581-109">Properties</span></span>

|<span data-ttu-id="63581-110">Propriedade</span><span class="sxs-lookup"><span data-stu-id="63581-110">Property</span></span> |<span data-ttu-id="63581-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="63581-111">Description</span></span> |
|---|---|
|<span data-ttu-id="63581-112">Nome</span><span class="sxs-lookup"><span data-stu-id="63581-112">Name</span></span> |<span data-ttu-id="63581-113">Indica o nome do pacote para o qual você deseja garantir um estado específico.</span><span class="sxs-lookup"><span data-stu-id="63581-113">Indicates the name of the package for you want to ensure a specific state.</span></span> |
|<span data-ttu-id="63581-114">SourcePath</span><span class="sxs-lookup"><span data-stu-id="63581-114">SourcePath</span></span> |<span data-ttu-id="63581-115">Indica o caminho em que o pacote reside.</span><span class="sxs-lookup"><span data-stu-id="63581-115">Indicates the path where the package resides.</span></span> |
|<span data-ttu-id="63581-116">LogPath</span><span class="sxs-lookup"><span data-stu-id="63581-116">LogPath</span></span> |<span data-ttu-id="63581-117">Indica o caminho completo em que você deseja que o provedor salve um arquivo de log para instalar ou desinstalar o pacote.</span><span class="sxs-lookup"><span data-stu-id="63581-117">Indicates the full path where you want the provider to save a log file to install or uninstall the package.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="63581-118">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="63581-118">Common properties</span></span>

|<span data-ttu-id="63581-119">Propriedade</span><span class="sxs-lookup"><span data-stu-id="63581-119">Property</span></span> |<span data-ttu-id="63581-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="63581-120">Description</span></span> |
|---|---|
|<span data-ttu-id="63581-121">DependsOn</span><span class="sxs-lookup"><span data-stu-id="63581-121">DependsOn</span></span> |<span data-ttu-id="63581-122">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="63581-122">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="63581-123">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="63581-123">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="63581-124">Ensure</span><span class="sxs-lookup"><span data-stu-id="63581-124">Ensure</span></span> |<span data-ttu-id="63581-125">Indica se o pacote foi instalado.</span><span class="sxs-lookup"><span data-stu-id="63581-125">Indicates if the package is installed.</span></span> <span data-ttu-id="63581-126">Defina esta propriedade como **Absent** para garantir que o pacote não seja instalado (ou desinstalar o pacote, se ele estiver instalado).</span><span class="sxs-lookup"><span data-stu-id="63581-126">Set this property to **Absent** to ensure the package is not installed (or uninstall the package if it is installed).</span></span> <span data-ttu-id="63581-127">Defina-a como **Present** para garantir que o pacote seja instalado.</span><span class="sxs-lookup"><span data-stu-id="63581-127">Set it to **Present** to ensure the package is installed.</span></span> <span data-ttu-id="63581-128">**Ensure** é uma propriedade obrigatória no recurso **WindowsPackageCab** .</span><span class="sxs-lookup"><span data-stu-id="63581-128">**Ensure** is a required property on the **WindowsPackageCab** resource.</span></span> |
|<span data-ttu-id="63581-129">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="63581-129">PsDscRunAsCredential</span></span> |<span data-ttu-id="63581-130">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="63581-130">Sets the credential for running the entire resource as.</span></span> |

## <a name="example"></a><span data-ttu-id="63581-131">Exemplo</span><span class="sxs-lookup"><span data-stu-id="63581-131">Example</span></span>

<span data-ttu-id="63581-132">A configuração de exemplo a seguir usa parâmetros de entrada e garante que o arquivo .cab especificado pelo parâmetro `$Name` esteja instalado.</span><span class="sxs-lookup"><span data-stu-id="63581-132">The following example configuration takes input parameters, and ensures that the .cab file specified by the `$Name` parameter is installed.</span></span>

```powershell
Configuration Sample_WindowsPackageCab
{
    param
    (
        [Parameter (Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $Name,

        [Parameter (Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $SourcePath,

        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $LogPath
    )

    Import-DscResource -ModuleName 'PSDscResources'

    WindowsPackageCab WindowsPackageCab1
    {
        Name = $Name
        Ensure = 'Present'
        SourcePath = $SourcePath
        LogPath = $LogPath
    }
}
```
