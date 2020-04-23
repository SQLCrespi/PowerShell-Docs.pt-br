---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso de DSC WindowsPackageCab
ms.openlocfilehash: ec465b2c3b1d180ba46ee24a61f2be1129148962
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "71954633"
---
# <a name="dsc-windowspackagecab-resource"></a><span data-ttu-id="e5474-103">Recurso de DSC WindowsPackageCab</span><span class="sxs-lookup"><span data-stu-id="e5474-103">DSC WindowsPackageCab Resource</span></span>

> <span data-ttu-id="e5474-104">Aplica-se a: Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="e5474-104">Applies To: Windows PowerShell 5.1</span></span>

<span data-ttu-id="e5474-105">O **WindowsPackageCab** no DSC (Desired State Configuration) do Windows PowerShell fornece um mecanismo para instalar ou desinstalar pacotes de gabinete (.cab) do Windows em um nó de destino.</span><span class="sxs-lookup"><span data-stu-id="e5474-105">The **WindowsPackageCab** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to install or uninstall Windows cabinet (.cab) packages on a target node.</span></span>

<span data-ttu-id="e5474-106">O nó de destino deve ter o módulo PowerShell do DISM instalado.</span><span class="sxs-lookup"><span data-stu-id="e5474-106">The target node must have the DISM PowerShell module installed.</span></span> <span data-ttu-id="e5474-107">Para obter informações, consulte [Usar DISM no Windows PowerShell](/windows-hardware/manufacture/desktop/use-dism-in-windows-powershell-s14).</span><span class="sxs-lookup"><span data-stu-id="e5474-107">For information, see [Use DISM in Windows PowerShell](/windows-hardware/manufacture/desktop/use-dism-in-windows-powershell-s14).</span></span>

## <a name="syntax"></a><span data-ttu-id="e5474-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e5474-108">Syntax</span></span>

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

## <a name="properties"></a><span data-ttu-id="e5474-109">Propriedades</span><span class="sxs-lookup"><span data-stu-id="e5474-109">Properties</span></span>

|<span data-ttu-id="e5474-110">Propriedade</span><span class="sxs-lookup"><span data-stu-id="e5474-110">Property</span></span> |<span data-ttu-id="e5474-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="e5474-111">Description</span></span> |
|---|---|
|<span data-ttu-id="e5474-112">Nome</span><span class="sxs-lookup"><span data-stu-id="e5474-112">Name</span></span> |<span data-ttu-id="e5474-113">Indica o nome do pacote para o qual você deseja garantir um estado específico.</span><span class="sxs-lookup"><span data-stu-id="e5474-113">Indicates the name of the package for you want to ensure a specific state.</span></span> |
|<span data-ttu-id="e5474-114">SourcePath</span><span class="sxs-lookup"><span data-stu-id="e5474-114">SourcePath</span></span> |<span data-ttu-id="e5474-115">Indica o caminho em que o pacote reside.</span><span class="sxs-lookup"><span data-stu-id="e5474-115">Indicates the path where the package resides.</span></span> |
|<span data-ttu-id="e5474-116">LogPath</span><span class="sxs-lookup"><span data-stu-id="e5474-116">LogPath</span></span> |<span data-ttu-id="e5474-117">Indica o caminho completo em que você deseja que o provedor salve um arquivo de log para instalar ou desinstalar o pacote.</span><span class="sxs-lookup"><span data-stu-id="e5474-117">Indicates the full path where you want the provider to save a log file to install or uninstall the package.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="e5474-118">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="e5474-118">Common properties</span></span>

|<span data-ttu-id="e5474-119">Propriedade</span><span class="sxs-lookup"><span data-stu-id="e5474-119">Property</span></span> |<span data-ttu-id="e5474-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="e5474-120">Description</span></span> |
|---|---|
|<span data-ttu-id="e5474-121">DependsOn</span><span class="sxs-lookup"><span data-stu-id="e5474-121">DependsOn</span></span> |<span data-ttu-id="e5474-122">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="e5474-122">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="e5474-123">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="e5474-123">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="e5474-124">Ensure</span><span class="sxs-lookup"><span data-stu-id="e5474-124">Ensure</span></span> |<span data-ttu-id="e5474-125">Indica se o pacote foi instalado.</span><span class="sxs-lookup"><span data-stu-id="e5474-125">Indicates if the package is installed.</span></span> <span data-ttu-id="e5474-126">Defina esta propriedade como **Absent** para garantir que o pacote não seja instalado (ou desinstalar o pacote, se ele estiver instalado).</span><span class="sxs-lookup"><span data-stu-id="e5474-126">Set this property to **Absent** to ensure the package is not installed (or uninstall the package if it is installed).</span></span> <span data-ttu-id="e5474-127">Defina-a como **Present** para garantir que o pacote seja instalado.</span><span class="sxs-lookup"><span data-stu-id="e5474-127">Set it to **Present** to ensure the package is installed.</span></span> <span data-ttu-id="e5474-128">**Ensure** é uma propriedade obrigatória no recurso **WindowsPackageCab**.</span><span class="sxs-lookup"><span data-stu-id="e5474-128">**Ensure** is a required property on the **WindowsPackageCab** resource.</span></span> |
|<span data-ttu-id="e5474-129">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="e5474-129">PsDscRunAsCredential</span></span> |<span data-ttu-id="e5474-130">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="e5474-130">Sets the credential for running the entire resource as.</span></span> |

## <a name="example"></a><span data-ttu-id="e5474-131">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e5474-131">Example</span></span>

<span data-ttu-id="e5474-132">A configuração de exemplo a seguir usa parâmetros de entrada e garante que o arquivo .cab especificado pelo parâmetro `$Name` esteja instalado.</span><span class="sxs-lookup"><span data-stu-id="e5474-132">The following example configuration takes input parameters, and ensures that the .cab file specified by the `$Name` parameter is installed.</span></span>

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