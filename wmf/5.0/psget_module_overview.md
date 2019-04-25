---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
ms.openlocfilehash: a0b1573611c5d4232082c19ca19b4cca79d0699e
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62057461"
---
# <a name="powershell-module-discovery-install-and-inventory-with-powershellget"></a><span data-ttu-id="2faca-102">Descoberta, instalação e inventário do módulo PowerShell com o PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="2faca-102">PowerShell Module Discovery, Install and Inventory with PowerShellGet</span></span>

<span data-ttu-id="2faca-103">O PowerShellGet está incluído nesta versão do WMF:</span><span class="sxs-lookup"><span data-stu-id="2faca-103">PowerShellGet is included in this release of WMF:</span></span>
-   <span data-ttu-id="2faca-104">Find-Module pode filtrar nos metadados do módulo com o parâmetro -Tag</span><span class="sxs-lookup"><span data-stu-id="2faca-104">Find-Module can filter on module metadata with the -Tag parameter</span></span>
-   <span data-ttu-id="2faca-105">Find-Module pode filtrar na linguagem de pesquisa específica do repositório com o parâmetro -Filter</span><span class="sxs-lookup"><span data-stu-id="2faca-105">Find-Module can filter on repository-specific search language with the -Filter parameter</span></span>
-   <span data-ttu-id="2faca-106">Find-Module pode filtrar no conteúdo do módulo com os parâmetros -Command, -DscResource e -Includes</span><span class="sxs-lookup"><span data-stu-id="2faca-106">Find-Module can filter based on module contents with the -Command, -DscResource, and -Includes parameters</span></span>
-   <span data-ttu-id="2faca-107">Find-DscResource permite a descoberta de recursos DSC individuais nos repositórios</span><span class="sxs-lookup"><span data-stu-id="2faca-107">Find-DscResource allows discovery of individual DSC resources in repositories</span></span>
-   <span data-ttu-id="2faca-108">Suporte para instalação desde compartilhamentos de arquivos e publicação neles com o NuGet</span><span class="sxs-lookup"><span data-stu-id="2faca-108">Support for installing from and publishing to file shares with NuGet</span></span>

## <a name="example-commands"></a><span data-ttu-id="2faca-109">Comandos de exemplo</span><span class="sxs-lookup"><span data-stu-id="2faca-109">Example commands</span></span>
```powershell
\# Find all modules with tags Azure or DSC
Find-Module -Tag Azure, DSC

\# Find modules with a specific DscResource
Find-Module -DscResource xFirewall

\#Find modules with specific commands
Find-Module -Command Get-ScriptAnalyzerRule, Invoke-ScriptAnalyzer

\# Find all modules with Dsc resources
Find-Module -Includes DscResource

\# Find all modules with cmdlets
Find-Module -Includes Cmdlet

\# Find all modules with functions
Find-Module -Includes Function

\# Find all DSC resources
Find-DscResource

\# Find all DSC resources contained within a specific module
Find-DscResource -ModuleName xNetworking

\# Find all DSC resources in modules with DSCResourceKit or DesiredStateConfiguration
Find-DscResource -Tag DesiredStateConfiguration, DSCResourceKit

\# Find modules using -Filter parameter
\# Specified filter value is searched in Name and Description properties
Find-Module -Filter Cookbook -Repository PSGallery
Find-Module -Filter RBAC -Repository PSGallery
```

## <a name="new-features-in-powershellget"></a><span data-ttu-id="2faca-110">Novos recursos no PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="2faca-110">New features in PowerShellGet</span></span>
-   <span data-ttu-id="2faca-111">Suporte à versão lado a lado no Windows PowerShell 5.0 ou mais recente</span><span class="sxs-lookup"><span data-stu-id="2faca-111">Side-by-side version support on Windows PowerShell 5.0 or newer</span></span>
-   <span data-ttu-id="2faca-112">Suporte à instalação de dependências do módulo</span><span class="sxs-lookup"><span data-stu-id="2faca-112">Module dependency installation support</span></span>
-   <span data-ttu-id="2faca-113">Três novos cmdlets</span><span class="sxs-lookup"><span data-stu-id="2faca-113">Three new cmdlets</span></span>
    -   <span data-ttu-id="2faca-114">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="2faca-114">Get-InstalledModule</span></span>
    -   <span data-ttu-id="2faca-115">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="2faca-115">Uninstall-Module</span></span>
    -   <span data-ttu-id="2faca-116">Save-Module</span><span class="sxs-lookup"><span data-stu-id="2faca-116">Save-Module</span></span>
