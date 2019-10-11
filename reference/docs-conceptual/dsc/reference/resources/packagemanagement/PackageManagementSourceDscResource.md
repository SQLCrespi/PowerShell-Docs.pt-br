---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso PackageManagementSource da DSC
ms.openlocfilehash: 20b7851e44751d4bd0add718d2f7294d5215ab70
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954783"
---
# <a name="dsc-packagemanagementsource-resource"></a><span data-ttu-id="a4792-103">Recurso PackageManagementSource da DSC</span><span class="sxs-lookup"><span data-stu-id="a4792-103">DSC PackageManagementSource Resource</span></span>

> <span data-ttu-id="a4792-104">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="a4792-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="a4792-105">O recurso **PackageManagementSource** na Configuração do Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para registrar ou cancelar o registro de fontes de Gerenciamento de Pacote em um nó de destino.</span><span class="sxs-lookup"><span data-stu-id="a4792-105">The **PackageManagementSource** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to register or unregister Package Management sources on a target node.</span></span>
<span data-ttu-id="a4792-106">**Fontes de Gerenciamento de Pacote registradas dessa forma são registradas no contexto do Sistema, podem ser usadas pela conta do Sistema ou pelo mecanismo de DSC.**</span><span class="sxs-lookup"><span data-stu-id="a4792-106">**Package Management sources registered in this way are registered under the System context, usable by the System account or by the DSC engine.**</span></span> <span data-ttu-id="a4792-107">Este recurso requer o módulo **PackageManagement**, disponível na [Galeria do PowerShell](https://PowerShellGallery.com).</span><span class="sxs-lookup"><span data-stu-id="a4792-107">This resource requires the **PackageManagement** module, available from the [PowerShell Gallery](https://PowerShellGallery.com).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4792-108">O módulo **PackageManagement** deve ser pelo menos a versão 1.1.7.0 para as informações de propriedade a seguir estarem corretas.</span><span class="sxs-lookup"><span data-stu-id="a4792-108">The **PackageManagement** module should be at least version 1.1.7.0 for the following property information to be correct.</span></span>

## <a name="syntax"></a><span data-ttu-id="a4792-109">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a4792-109">Syntax</span></span>

```Syntax
PackageManagementSource [String] #ResourceName
{
    Name = [string]
    ProviderName = [string]
    SourceLocation = [string]
    [ InstallationPolicy = [string]{ Trusted | Untrusted } ]
    [ SourceCredential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string]{ Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="a4792-110">Propriedades</span><span class="sxs-lookup"><span data-stu-id="a4792-110">Properties</span></span>

|<span data-ttu-id="a4792-111">Propriedade</span><span class="sxs-lookup"><span data-stu-id="a4792-111">Property</span></span> |<span data-ttu-id="a4792-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="a4792-112">Description</span></span> |
|---|---|
|<span data-ttu-id="a4792-113">Nome</span><span class="sxs-lookup"><span data-stu-id="a4792-113">Name</span></span> |<span data-ttu-id="a4792-114">Especifica o nome da origem do pacote a ser registrado ou cancelado no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="a4792-114">Specifies the name of the package source to be registered or unregistered on your system.</span></span> |
|<span data-ttu-id="a4792-115">ProviderName</span><span class="sxs-lookup"><span data-stu-id="a4792-115">ProviderName</span></span> |<span data-ttu-id="a4792-116">Especifica o nome do provedor OneGet por meio do qual você pode fornecer interoperabilidade com a origem do pacote.</span><span class="sxs-lookup"><span data-stu-id="a4792-116">Specifies the name of the OneGet provider through which you can interop with the package source.</span></span> |
|<span data-ttu-id="a4792-117">SourceLocation</span><span class="sxs-lookup"><span data-stu-id="a4792-117">SourceLocation</span></span> |<span data-ttu-id="a4792-118">Especifica o URI de origem do pacote.</span><span class="sxs-lookup"><span data-stu-id="a4792-118">Specifies the URI of the package source.</span></span> |
|<span data-ttu-id="a4792-119">InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="a4792-119">InstallationPolicy</span></span> |<span data-ttu-id="a4792-120">Usada por provedores como o Nuget interno.</span><span class="sxs-lookup"><span data-stu-id="a4792-120">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="a4792-121">Determina se você confia na origem do pacote.</span><span class="sxs-lookup"><span data-stu-id="a4792-121">Determines whether you trust the package's source.</span></span> <span data-ttu-id="a4792-122">Um destes: **Não confiável** ou **Confiável**.</span><span class="sxs-lookup"><span data-stu-id="a4792-122">One of: **Untrusted** or **Trusted**.</span></span> |
|<span data-ttu-id="a4792-123">SourceCredential</span><span class="sxs-lookup"><span data-stu-id="a4792-123">SourceCredential</span></span> |<span data-ttu-id="a4792-124">Fornece acesso ao pacote em uma fonte remota.</span><span class="sxs-lookup"><span data-stu-id="a4792-124">Provides access to the package on a remote source.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="a4792-125">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="a4792-125">Common properties</span></span>

|<span data-ttu-id="a4792-126">Propriedade</span><span class="sxs-lookup"><span data-stu-id="a4792-126">Property</span></span> |<span data-ttu-id="a4792-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="a4792-127">Description</span></span> |
|---|---|
|<span data-ttu-id="a4792-128">DependsOn</span><span class="sxs-lookup"><span data-stu-id="a4792-128">DependsOn</span></span> |<span data-ttu-id="a4792-129">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="a4792-129">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="a4792-130">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="a4792-130">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="a4792-131">Ensure</span><span class="sxs-lookup"><span data-stu-id="a4792-131">Ensure</span></span> |<span data-ttu-id="a4792-132">Determina se a origem do pacote deve ser registrada ou cancelada.</span><span class="sxs-lookup"><span data-stu-id="a4792-132">Determines whether the package source is to be registered or unregistered.</span></span> <span data-ttu-id="a4792-133">O valor padrão é **Present**.</span><span class="sxs-lookup"><span data-stu-id="a4792-133">The default value is **Present**.</span></span> |
|<span data-ttu-id="a4792-134">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="a4792-134">PsDscRunAsCredential</span></span> |<span data-ttu-id="a4792-135">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="a4792-135">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="a4792-136">A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais.</span><span class="sxs-lookup"><span data-stu-id="a4792-136">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="a4792-137">Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="a4792-137">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="a4792-138">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a4792-138">Example</span></span>

<span data-ttu-id="a4792-139">Este exemplo registra a origem do pacote de `https://nuget.org` usando o recurso DSC **PackageManagementSource**.</span><span class="sxs-lookup"><span data-stu-id="a4792-139">This example registers the `https://nuget.org` package source using the **PackageManagementSource** DSC resource.</span></span>

```powershell
Configuration PackageManagementSourceTest
{
    PackageManagementSource SourceRepository
    {
        Ensure      = "Present"
        Name        = "MyNuget"
        ProviderName= "Nuget"
        SourceLocation   = "https://api.nuget.org/api/v3/"
        InstallationPolicy ="Trusted"
    }
}
```