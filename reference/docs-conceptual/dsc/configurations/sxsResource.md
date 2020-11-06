---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Importar uma versão específica de um recurso instalado
description: Este artigo mostra como instalar e importar versões específicas de módulos de recursos em suas configurações.
ms.openlocfilehash: bb7b3273a5a3fed94fecd90dd3ea1e623fbc332b
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92645045"
---
# <a name="import-a-specific-version-of-an-installed-resource"></a><span data-ttu-id="c9d38-104">Importar uma versão específica de um recurso instalado</span><span class="sxs-lookup"><span data-stu-id="c9d38-104">Import a specific version of an installed resource</span></span>

> <span data-ttu-id="c9d38-105">Aplica-se a: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="c9d38-105">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="c9d38-106">No PowerShell 5.0, versões separadas de recursos DSC podem ser instaladas em um computador lado a lado.</span><span class="sxs-lookup"><span data-stu-id="c9d38-106">In PowerShell 5.0, separate versions of DSC resources can be installed on a computer side by side.</span></span> <span data-ttu-id="c9d38-107">Um módulo de recursos pode armazenar versões separadas de um recurso em pastas nomeadas por versão.</span><span class="sxs-lookup"><span data-stu-id="c9d38-107">A resource module can store separate versions of a resource in version named folders.</span></span>

## <a name="installing-separate-resource-versions-side-by-side"></a><span data-ttu-id="c9d38-108">Instalando versões separadas de recursos lado a lado</span><span class="sxs-lookup"><span data-stu-id="c9d38-108">Installing separate resource versions side by side</span></span>

<span data-ttu-id="c9d38-109">Você pode usar os parâmetros **MinimumVersion** , **MaximumVersion** e **RequiredVersion** do cmdlet [Install-Module](/powershell/module/PowershellGet/Install-Module) para especificar qual versão de um módulo instalar.</span><span class="sxs-lookup"><span data-stu-id="c9d38-109">You can use the **MinimumVersion** , **MaximumVersion** , and **RequiredVersion** parameters of the [Install-Module](/powershell/module/PowershellGet/Install-Module) cmdlet to specify which version of a module to install.</span></span> <span data-ttu-id="c9d38-110">Se você chamar **Install-Module** sem especificar uma versão, a versão mais recente será instalada.</span><span class="sxs-lookup"><span data-stu-id="c9d38-110">Calling **Install-Module** without specifying a version installs the most recent version.</span></span>

<span data-ttu-id="c9d38-111">Por exemplo, há várias versões do módulo **xFailOverCluster** , cada uma com um recurso **xCluster**.</span><span class="sxs-lookup"><span data-stu-id="c9d38-111">For example, there are multiple versions of the **xFailOverCluster** module, each of which contains an **xCluster** resource.</span></span> <span data-ttu-id="c9d38-112">Chamar **Install-Module** sem especificar o número de uma versão instala a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="c9d38-112">Calling **Install-Module** without specifying the version number installs the most recent version of the module.</span></span>

```powershell
PS> Install-Module xFailOverCluster
PS> Get-DscResource xCluster
```

```Output
ImplementedAs   Name          ModuleName           Version    Properties
-------------   ----          ----------           -------    ----------
PowerShell      xCluster      xFailOverCluster     1.2.0.0    {DomainAdministratorCredential, ...
```

<span data-ttu-id="c9d38-113">Para instalar a versão específica de um módulo, especifique **RequiredVersion** de 1.1.0.0.</span><span class="sxs-lookup"><span data-stu-id="c9d38-113">To install a specific version of a module, specify a **RequiredVersion** of 1.1.0.0.</span></span> <span data-ttu-id="c9d38-114">Isso instala a versão especificada lado a lado com a versão instalada.</span><span class="sxs-lookup"><span data-stu-id="c9d38-114">This installs the specified version side by side with the installed version.</span></span>

```powershell
PS> Install-Module xFailOverCluster -RequiredVersion 1.1
```

<span data-ttu-id="c9d38-115">Agora você verá as duas versões do módulo listadas ao usar `Get-DSCResource`.</span><span class="sxs-lookup"><span data-stu-id="c9d38-115">Now, you see both version of the module listed when you use `Get-DSCResource`.</span></span>

```powershell
PS> Get-DscResource xCluster
```

```Output
ImplementedAs   Name          ModuleName            Version    Properties
-------------   ----          ----------            -------    ----------
PowerShell      xCluster      xFailOverCluster      1.1        {DomainAdministratorCredential, Name, ...
PowerShell      xCluster      xFailOverCluster      1.2.0.0    {DomainAdministratorCredential, Name, ...
```

## <a name="specifying-a-resource-version-in-a-configuration"></a><span data-ttu-id="c9d38-116">Especificando uma versão do recurso em uma configuração</span><span class="sxs-lookup"><span data-stu-id="c9d38-116">Specifying a resource version in a configuration</span></span>

<span data-ttu-id="c9d38-117">Se você tiver recursos separados instalados em um computador, deve especificar a versão do recurso ao usá-lo em uma configuração.</span><span class="sxs-lookup"><span data-stu-id="c9d38-117">If you have separate resource versions installed on a computer, you must specify the version of that resource when you use it in a configuration.</span></span> <span data-ttu-id="c9d38-118">Faça isso especificando o parâmetro **ModuleVersion** da palavra-chave **Import-DscResource**.</span><span class="sxs-lookup"><span data-stu-id="c9d38-118">You do this by specifying the **ModuleVersion** parameter of the **Import-DscResource** keyword.</span></span> <span data-ttu-id="c9d38-119">Se você não especificar a versão de um módulo de um recurso do qual tem mais de uma versão instalada, a configuração vai gerar um erro.</span><span class="sxs-lookup"><span data-stu-id="c9d38-119">If you fail to specify the version of a resource module of a resource of which you have more than one version installed, the configuration generates an error.</span></span>

<span data-ttu-id="c9d38-120">A configuração a seguir mostra como especificar a versão do recurso a ser chamado:</span><span class="sxs-lookup"><span data-stu-id="c9d38-120">The following configuration shows how to specify the version of the resource to call:</span></span>

```powershell
configuration VersionTest
{
    Import-DscResource -ModuleName xFailOverCluster -ModuleVersion 1.1

    Node 'localhost'
    {
       xCluster ClusterTest
       {
            Name                          = 'TestCluster'
            StaticIPAddress               = '10.0.0.3'
            DomainAdministratorCredential = Get-Credential
        }
     }
}
```

<span data-ttu-id="c9d38-121">o parâmetro ModuleVersion de Import-DscResource não está disponível no PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="c9d38-121">The ModuleVersion parameter of Import-DscResource is not available in PowerShell 4.0.</span></span> <span data-ttu-id="c9d38-122">No PowerShell 4.0, é possível especificar uma versão de módulo passando um objeto de especificação de módulo para o parâmetro ModuleName de Import-DscResource.</span><span class="sxs-lookup"><span data-stu-id="c9d38-122">In PowerShell 4.0, you can specify a module version by passing a module specification object to the ModuleName parameter of Import-DscResource.</span></span> <span data-ttu-id="c9d38-123">Um objeto de especificação de módulo é uma tabela de hash que contém as chaves ModuleName e RequiredVersion.</span><span class="sxs-lookup"><span data-stu-id="c9d38-123">A module specification object is a hash table that contains ModuleName and RequiredVersion keys.</span></span> <span data-ttu-id="c9d38-124">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c9d38-124">For example:</span></span>

```powershell
configuration VersionTest
{
    Import-DscResource -ModuleName (@{ModuleName='xFailOverCluster'; RequiredVersion='1.1'} )

    Node 'localhost'
    {
       xCluster ClusterTest
       {
            Name                          = 'TestCluster'
            StaticIPAddress               = '10.0.0.3'
            DomainAdministratorCredential = Get-Credential
        }
     }
}
```

<span data-ttu-id="c9d38-125">Isso também funcionará no PowerShell 5.0, mas é recomendável que você use o parâmetro **ModuleVersion**.</span><span class="sxs-lookup"><span data-stu-id="c9d38-125">This will also work in PowerShell 5.0, but it is recommended that you use the **ModuleVersion** parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="c9d38-126">Veja também</span><span class="sxs-lookup"><span data-stu-id="c9d38-126">See also</span></span>

- [<span data-ttu-id="c9d38-127">Configurações DSC</span><span class="sxs-lookup"><span data-stu-id="c9d38-127">DSC Configurations</span></span>](configurations.md)
- [<span data-ttu-id="c9d38-128">Recursos de DSC</span><span class="sxs-lookup"><span data-stu-id="c9d38-128">DSC Resources</span></span>](../resources/resources.md)
