---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso PackageManagement de DSC
ms.openlocfilehash: 28ae8772170bd4559c8a19c3a1df8c9118734857
ms.sourcegitcommit: bc9a4904c2b1561386d748fc9ac242699d2f1694
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "76995974"
---
# <a name="dsc-packagemanagement-resource"></a><span data-ttu-id="b15c0-103">Recurso PackageManagement de DSC</span><span class="sxs-lookup"><span data-stu-id="b15c0-103">DSC PackageManagement Resource</span></span>

<span data-ttu-id="b15c0-104">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.0, Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="b15c0-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0, Windows PowerShell 5.1</span></span>

<span data-ttu-id="b15c0-105">O recurso **PackageManagement** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para instalar ou desinstalar pacotes de Gerenciamento de Pacotes em um nó de destino.</span><span class="sxs-lookup"><span data-stu-id="b15c0-105">The **PackageManagement** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to install or uninstall Package Management packages on a target node.</span></span> <span data-ttu-id="b15c0-106">Este recurso requer o módulo **PackageManagement**, disponível em [https://PowerShellGallery.com](https://PowerShellGallery.com).</span><span class="sxs-lookup"><span data-stu-id="b15c0-106">This resource requires the **PackageManagement** module, available from [https://PowerShellGallery.com](https://PowerShellGallery.com).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b15c0-107">O módulo **PackageManagement** deve ser pelo menos a versão 1.1.7.0 para as informações de propriedade a seguir estarem corretas.</span><span class="sxs-lookup"><span data-stu-id="b15c0-107">The **PackageManagement** module should be at least version 1.1.7.0 for the following property information to be correct.</span></span>

## <a name="syntax"></a><span data-ttu-id="b15c0-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b15c0-108">Syntax</span></span>

```Syntax
PackageManagement [string] #ResourceName
{
    Name = [string]
    [ AdditionalParameters = [HashTable] ]
    [ MaximumVersion = [string] ]
    [ MinimumVersion = [string] ]
    [ ProviderName = [string] ]
    [ RequiredVersion = [string] ]
    [ Source = [string] ]
    [ SourceCredential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string]{ Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="b15c0-109">Propriedades</span><span class="sxs-lookup"><span data-stu-id="b15c0-109">Properties</span></span>

|<span data-ttu-id="b15c0-110">Propriedade</span><span class="sxs-lookup"><span data-stu-id="b15c0-110">Property</span></span> |<span data-ttu-id="b15c0-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="b15c0-111">Description</span></span> |
|---|---|
|<span data-ttu-id="b15c0-112">Nome</span><span class="sxs-lookup"><span data-stu-id="b15c0-112">Name</span></span> |<span data-ttu-id="b15c0-113">Especifica o nome do Pacote a ser instalado ou desinstalado.</span><span class="sxs-lookup"><span data-stu-id="b15c0-113">Specifies the name of the Package to be installed or uninstalled.</span></span> |
|<span data-ttu-id="b15c0-114">AdditionalParameters</span><span class="sxs-lookup"><span data-stu-id="b15c0-114">AdditionalParameters</span></span> |<span data-ttu-id="b15c0-115">Tabela de hash específica do provedor dos parâmetros que seria passado para o `Get-Package -AdditionalArguments`.</span><span class="sxs-lookup"><span data-stu-id="b15c0-115">Provider specific hashtable of parameters that would be passed to `Get-Package -AdditionalArguments`.</span></span> <span data-ttu-id="b15c0-116">Por exemplo, para o provedor do NuGet, você pode transmitir parâmetros adicionais, como DestinationPath.</span><span class="sxs-lookup"><span data-stu-id="b15c0-116">For example, for NuGet provider you can pass additional parameters like DestinationPath.</span></span> |
|<span data-ttu-id="b15c0-117">MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="b15c0-117">MaximumVersion</span></span> |<span data-ttu-id="b15c0-118">Especifica a versão máxima permitida do pacote que você deseja encontrar.</span><span class="sxs-lookup"><span data-stu-id="b15c0-118">Specifies the maximum allowed version of the package that you want to find.</span></span> <span data-ttu-id="b15c0-119">Se você não adicionar esse parâmetro, o recurso localizará a versão mais recente disponível do pacote.</span><span class="sxs-lookup"><span data-stu-id="b15c0-119">If you do not add this parameter, the resource finds the highest available version of the package.</span></span> |
|<span data-ttu-id="b15c0-120">MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="b15c0-120">MinimumVersion</span></span> |<span data-ttu-id="b15c0-121">Especifica a versão mínima permitida do pacote que você deseja encontrar.</span><span class="sxs-lookup"><span data-stu-id="b15c0-121">Specifies the minimum allowed version of the package that you want to find.</span></span> <span data-ttu-id="b15c0-122">Se você não adicionar esse parâmetro, esse recurso encontrará a versão disponível mais recente do pacote que também atende a qualquer versão máxima especificada pelo parâmetro **MaximumVersion**.</span><span class="sxs-lookup"><span data-stu-id="b15c0-122">If you do not add this parameter, the resource finds the highest available version of the package that also satisfies any maximum specified version specified by the **MaximumVersion** parameter.</span></span> |
|<span data-ttu-id="b15c0-123">ProviderName</span><span class="sxs-lookup"><span data-stu-id="b15c0-123">ProviderName</span></span> |<span data-ttu-id="b15c0-124">Especifica um nome de provedor de pacote para o qual definir o escopo de sua pesquisa de pacote.</span><span class="sxs-lookup"><span data-stu-id="b15c0-124">Specifies a package provider name to which to scope your package search.</span></span> <span data-ttu-id="b15c0-125">Você pode obter os nomes de provedor de pacotes executando o cmdlet `Get-PackageProvider`.</span><span class="sxs-lookup"><span data-stu-id="b15c0-125">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span> |
|<span data-ttu-id="b15c0-126">RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="b15c0-126">RequiredVersion</span></span> |<span data-ttu-id="b15c0-127">Especifica a versão exata do pacote que você deseja instalar.</span><span class="sxs-lookup"><span data-stu-id="b15c0-127">Specifies the exact version of the package that you want to install.</span></span> <span data-ttu-id="b15c0-128">Se você não especificar esse parâmetro, esse recurso DSC instalará a versão disponível mais recente do pacote que também atende a qualquer versão máxima especificada pelo parâmetro **MaximumVersion**.</span><span class="sxs-lookup"><span data-stu-id="b15c0-128">If you do not specify this parameter, this DSC resource installs the newest available version of the package that also satisfies any maximum version specified by the **MaximumVersion** parameter.</span></span> |
|<span data-ttu-id="b15c0-129">Fonte</span><span class="sxs-lookup"><span data-stu-id="b15c0-129">Source</span></span> |<span data-ttu-id="b15c0-130">Especifica o nome da origem do pacote onde é possível encontrar o pacote.</span><span class="sxs-lookup"><span data-stu-id="b15c0-130">Specifies the name of the package source where the package can be found.</span></span> <span data-ttu-id="b15c0-131">Isso pode ser um URI ou uma fonte registrada com o recurso de DSC `Register-PackageSource` ou PackageManagementSource.</span><span class="sxs-lookup"><span data-stu-id="b15c0-131">This can either be a URI or a source registered with `Register-PackageSource` or PackageManagementSource DSC resource.</span></span> |
|<span data-ttu-id="b15c0-132">SourceCredential</span><span class="sxs-lookup"><span data-stu-id="b15c0-132">SourceCredential</span></span> |<span data-ttu-id="b15c0-133">Especifica uma conta de usuário que tenha direitos para instalar um pacote para um provedor de pacote ou origem específicos.</span><span class="sxs-lookup"><span data-stu-id="b15c0-133">Specifies a user account that has rights to install a package for a specified package provider or source.</span></span> |

## <a name="additional-parameters"></a><span data-ttu-id="b15c0-134">Parâmetros Adicionais</span><span class="sxs-lookup"><span data-stu-id="b15c0-134">Additional Parameters</span></span>

<span data-ttu-id="b15c0-135">A tabela a seguir lista as opções para a propriedade AdditionalParameters.</span><span class="sxs-lookup"><span data-stu-id="b15c0-135">The following table lists options for the AdditionalParameters property.</span></span>

|<span data-ttu-id="b15c0-136">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="b15c0-136">Parameter</span></span> |<span data-ttu-id="b15c0-137">Descrição</span><span class="sxs-lookup"><span data-stu-id="b15c0-137">Description</span></span> |
|---|---|
|<span data-ttu-id="b15c0-138">DestinationPath</span><span class="sxs-lookup"><span data-stu-id="b15c0-138">DestinationPath</span></span> |<span data-ttu-id="b15c0-139">Usada por provedores como o Nuget interno.</span><span class="sxs-lookup"><span data-stu-id="b15c0-139">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="b15c0-140">Especifica o local de um arquivo onde você deseja que o pacote seja instalado.</span><span class="sxs-lookup"><span data-stu-id="b15c0-140">Specifies a file location where you want the package to be installed.</span></span> |
|<span data-ttu-id="b15c0-141">InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="b15c0-141">InstallationPolicy</span></span> |<span data-ttu-id="b15c0-142">Usada por provedores como o Nuget interno.</span><span class="sxs-lookup"><span data-stu-id="b15c0-142">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="b15c0-143">Determina se você confia na origem do pacote.</span><span class="sxs-lookup"><span data-stu-id="b15c0-143">Determines whether you trust the package's source.</span></span> <span data-ttu-id="b15c0-144">Um destes: **Não confiável** ou **Confiável**.</span><span class="sxs-lookup"><span data-stu-id="b15c0-144">One of: **Untrusted** or **Trusted**.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="b15c0-145">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="b15c0-145">Common properties</span></span>

|<span data-ttu-id="b15c0-146">Propriedade</span><span class="sxs-lookup"><span data-stu-id="b15c0-146">Property</span></span> |<span data-ttu-id="b15c0-147">Descrição</span><span class="sxs-lookup"><span data-stu-id="b15c0-147">Description</span></span> |
|---|---|
|<span data-ttu-id="b15c0-148">DependsOn</span><span class="sxs-lookup"><span data-stu-id="b15c0-148">DependsOn</span></span> |<span data-ttu-id="b15c0-149">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="b15c0-149">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="b15c0-150">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="b15c0-150">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="b15c0-151">Ensure</span><span class="sxs-lookup"><span data-stu-id="b15c0-151">Ensure</span></span> |<span data-ttu-id="b15c0-152">Determina se o pacote deve ser instalado ou desinstalado.</span><span class="sxs-lookup"><span data-stu-id="b15c0-152">Determines whether the package is to be installed or uninstalled.</span></span> <span data-ttu-id="b15c0-153">O valor padrão é **Present**.</span><span class="sxs-lookup"><span data-stu-id="b15c0-153">The default value is **Present**.</span></span> |
|<span data-ttu-id="b15c0-154">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="b15c0-154">PsDscRunAsCredential</span></span> |<span data-ttu-id="b15c0-155">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="b15c0-155">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="b15c0-156">A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais.</span><span class="sxs-lookup"><span data-stu-id="b15c0-156">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="b15c0-157">Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="b15c0-157">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="b15c0-158">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b15c0-158">Example</span></span>

<span data-ttu-id="b15c0-159">Este exemplo instala o pacote do NuGet **JQuery** e o módulo do PowerShell **GistProvider** usando o recurso de DSC **PackageManagement**.</span><span class="sxs-lookup"><span data-stu-id="b15c0-159">This example installs the **JQuery** NuGet package and **GistProvider** PowerShell module using the **PackageManagement** DSC resource.</span></span> <span data-ttu-id="b15c0-160">Este exemplo primeiro garante que as origens dos pacotes necessários estejam disponíveis e, em seguida, define o estado esperado dos pacotes **JQuery** e **GistProvider** (NuGet e PowerShell, respectivamente).</span><span class="sxs-lookup"><span data-stu-id="b15c0-160">This example first ensures the required package sources are available then defines the expected state of the **JQuery** and **GistProvider** packages (NuGet and PowerShell, respectively).</span></span>

```powershell
Configuration PackageTest
{
    PackageManagementSource SourceRepository
    {
        Ensure      = "Present"
        Name        = "MyNuget"
        ProviderName= "Nuget"
        SourceLocation   = "http://nuget.org/api/v2/"
        InstallationPolicy ="Trusted"
    }

    PackageManagementSource PSGallery
    {
        Ensure      = "Present"
        Name        = "psgallery"
        ProviderName= "PowerShellGet"
        SourceLocation   = "https://www.powershellgallery.com/api/v2"
        InstallationPolicy ="Trusted"
    }

    PackageManagement NugetPackage
    {
        Ensure               = "Present"
        Name                 = "JQuery"
        AdditionalParameters = "$env:HomeDrive\nuget"
        RequiredVersion      = "2.0.1"
        DependsOn            = "[PackageManagementSource]SourceRepository"
    }

    PackageManagement PSModule
    {
        Ensure               = "Present"
        Name                 = "gistprovider"
        Source               = "PSGallery"
        DependsOn            = "[PackageManagementSource]PSGallery"
    }
}
```