---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Atualizar nós de um servidor de pull
ms.openlocfilehash: 516e50b0c39e4747a123307cb3f5e25259ac7ce5
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74417705"
---
# <a name="update-nodes-from-a-pull-server"></a><span data-ttu-id="3b273-103">Atualizar nós de um servidor de pull</span><span class="sxs-lookup"><span data-stu-id="3b273-103">Update Nodes from a Pull Server</span></span>

<span data-ttu-id="3b273-104">As seções a seguir pressupõem que você já tenha configurado um servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="3b273-104">The sections below assume that you have already set up a Pull Server.</span></span> <span data-ttu-id="3b273-105">Se ainda não configurou, use os guias a seguir:</span><span class="sxs-lookup"><span data-stu-id="3b273-105">If you have not set up your Pull Server, you can use the following guides:</span></span>

- [<span data-ttu-id="3b273-106">Configurar um servidor de pull SMB de DSC</span><span class="sxs-lookup"><span data-stu-id="3b273-106">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="3b273-107">Configurar um servidor de pull HTTP de DSC</span><span class="sxs-lookup"><span data-stu-id="3b273-107">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="3b273-108">Cada nó de destino pode ser configurado para baixar configurações, recursos e até mesmo relatar seu status.</span><span class="sxs-lookup"><span data-stu-id="3b273-108">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="3b273-109">Este artigo mostrará como carregar recursos para que fiquem disponíveis para download e como configurar clientes para baixar os recursos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3b273-109">This article will show you how to upload resources so they are available to be downloaded, and configure clients to download resources automatically.</span></span> <span data-ttu-id="3b273-110">Quando o nó recebe uma configuração atribuída, por meio de **Pull** ou **Push** (v5), ele baixa automaticamente todos os recursos necessários para a configuração do local especificado no LCM.</span><span class="sxs-lookup"><span data-stu-id="3b273-110">When the Node's receives an assigned Configuration, through **Pull** or **Push** (v5), it automatically downloads any resources required by the Configuration from the location specified in the LCM.</span></span>

## <a name="using-the-update-dscconfiguration-cmdlet"></a><span data-ttu-id="3b273-111">Usando o cmdlet Update-DSCConfiguration</span><span class="sxs-lookup"><span data-stu-id="3b273-111">Using the Update-DSCConfiguration cmdlet</span></span>

<span data-ttu-id="3b273-112">A partir do PowerShell 5.0, o cmdlet [Update-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/update-dscconfiguration) força um nó a atualizar sua configuração do servidor de pull configurado no LCM.</span><span class="sxs-lookup"><span data-stu-id="3b273-112">Beginning in PowerShell 5.0, the [Update-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/update-dscconfiguration) cmdlet, forces a Node to update its configuration from the Pull Server configured in the LCM.</span></span>

```powershell
Update-DSCConfiguration -ComputerName "Server01"
```

## <a name="using-invoke-cimmethod"></a><span data-ttu-id="3b273-113">Usando Invoke-CIMMethod</span><span class="sxs-lookup"><span data-stu-id="3b273-113">Using Invoke-CIMMethod</span></span>

<span data-ttu-id="3b273-114">No PowerShell 4.0, você ainda pode forçar manualmente um cliente de Pull para atualizar sua configuração usando [Invoke-CIMMethod](/powershell/module/cimcmdlets/invoke-cimmethod).</span><span class="sxs-lookup"><span data-stu-id="3b273-114">In PowerShell 4.0, you can still manually force a Pull Client to update its Configuration using [Invoke-CIMMethod](/powershell/module/cimcmdlets/invoke-cimmethod).</span></span> <span data-ttu-id="3b273-115">O exemplo a seguir cria uma sessão CIM com as credenciais especificadas, invoca o método CIM apropriado e remove a sessão.</span><span class="sxs-lookup"><span data-stu-id="3b273-115">The following example creates a CIM session with specified credentials, invokes the appropriate CIM method, and removes the session.</span></span>

```powershell
$cimSession = New-CimSession -ComputerName "Server01" -Credential $(Get-Credential)
Invoke-CimMethod -CimSession $cimSession -Namespace 'root/microsoft/windows/desiredstateconfiguration' -Class 'MSFT_DscLocalConfigurationManager' -MethodName 'PerformRequiredConfigurationChecks' -Arguments @{ 'Flags' = [uint32]1 } -Verbose
$cimSession | Remove-CimSession
```

## <a name="see-also"></a><span data-ttu-id="3b273-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3b273-116">See Also</span></span>

[<span data-ttu-id="3b273-117">PerformRequiredConfigurationChecks</span><span class="sxs-lookup"><span data-stu-id="3b273-117">PerformRequiredConfigurationChecks</span></span>](/powershell/scripting/dsc/msft-dsclocalconfigurationmanager-performrequiredconfigurationchecks)
