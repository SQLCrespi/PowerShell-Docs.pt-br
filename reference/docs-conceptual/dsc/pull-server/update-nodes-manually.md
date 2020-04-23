---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Atualizar nós de um servidor de pull
ms.openlocfilehash: fa59a2f6574db2dbc96621be4326f1d5a55e5de9
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "80500671"
---
# <a name="update-nodes-from-a-pull-server"></a><span data-ttu-id="14e75-103">Atualizar nós de um servidor de pull</span><span class="sxs-lookup"><span data-stu-id="14e75-103">Update Nodes from a Pull Server</span></span>

<span data-ttu-id="14e75-104">As seções a seguir pressupõem que você já tenha configurado um servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="14e75-104">The sections below assume that you have already set up a Pull Server.</span></span> <span data-ttu-id="14e75-105">Se ainda não configurou, use os guias a seguir:</span><span class="sxs-lookup"><span data-stu-id="14e75-105">If you have not set up your Pull Server, you can use the following guides:</span></span>

- [<span data-ttu-id="14e75-106">Configurar um servidor de pull SMB de DSC</span><span class="sxs-lookup"><span data-stu-id="14e75-106">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="14e75-107">Configurar um servidor de pull HTTP de DSC</span><span class="sxs-lookup"><span data-stu-id="14e75-107">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="14e75-108">Cada nó de destino pode ser configurado para baixar configurações, recursos e até mesmo relatar seu status.</span><span class="sxs-lookup"><span data-stu-id="14e75-108">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="14e75-109">Este artigo mostrará como carregar recursos para que fiquem disponíveis para download e como configurar clientes para baixar os recursos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="14e75-109">This article will show you how to upload resources so they are available to be downloaded, and configure clients to download resources automatically.</span></span> <span data-ttu-id="14e75-110">Quando o nó recebe uma configuração atribuída, por meio de **Pull** ou **Push** (v5), ele baixa automaticamente todos os recursos necessários para a configuração do local especificado no LCM.</span><span class="sxs-lookup"><span data-stu-id="14e75-110">When the Node's receives an assigned Configuration, through **Pull** or **Push** (v5), it automatically downloads any resources required by the Configuration from the location specified in the LCM.</span></span>

## <a name="using-the-update-dscconfiguration-cmdlet"></a><span data-ttu-id="14e75-111">Usando o cmdlet Update-DSCConfiguration</span><span class="sxs-lookup"><span data-stu-id="14e75-111">Using the Update-DSCConfiguration cmdlet</span></span>

<span data-ttu-id="14e75-112">A partir do PowerShell 5.0, o cmdlet [Update-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/update-dscconfiguration) força um nó a atualizar sua configuração do servidor de pull configurado no LCM.</span><span class="sxs-lookup"><span data-stu-id="14e75-112">Beginning in PowerShell 5.0, the [Update-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/update-dscconfiguration) cmdlet, forces a Node to update its configuration from the Pull Server configured in the LCM.</span></span>

```powershell
Update-DSCConfiguration -ComputerName "Server01"
```

## <a name="using-invoke-cimmethod"></a><span data-ttu-id="14e75-113">Usando Invoke-CIMMethod</span><span class="sxs-lookup"><span data-stu-id="14e75-113">Using Invoke-CIMMethod</span></span>

<span data-ttu-id="14e75-114">No PowerShell 4.0, você ainda pode forçar manualmente um cliente de Pull para atualizar sua configuração usando [Invoke-CIMMethod](/powershell/module/cimcmdlets/invoke-cimmethod).</span><span class="sxs-lookup"><span data-stu-id="14e75-114">In PowerShell 4.0, you can still manually force a Pull Client to update its Configuration using [Invoke-CIMMethod](/powershell/module/cimcmdlets/invoke-cimmethod).</span></span> <span data-ttu-id="14e75-115">O exemplo a seguir cria uma sessão CIM com as credenciais especificadas, invoca o método CIM apropriado e remove a sessão.</span><span class="sxs-lookup"><span data-stu-id="14e75-115">The following example creates a CIM session with specified credentials, invokes the appropriate CIM method, and removes the session.</span></span>

```powershell
$cimSession = New-CimSession -ComputerName "Server01" -Credential $(Get-Credential)
Invoke-CimMethod -CimSession $cimSession -Namespace 'root/microsoft/windows/desiredstateconfiguration' -Class 'MSFT_DscLocalConfigurationManager' -MethodName 'PerformRequiredConfigurationChecks' -Arguments @{ 'Flags' = [uint32]1 } -Verbose
$cimSession | Remove-CimSession
```

## <a name="see-also"></a><span data-ttu-id="14e75-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="14e75-116">See Also</span></span>

[<span data-ttu-id="14e75-117">PerformRequiredConfigurationChecks</span><span class="sxs-lookup"><span data-stu-id="14e75-117">PerformRequiredConfigurationChecks</span></span>](../reference/mof-classes/msft-dsclocalconfigurationmanager-performrequiredconfigurationchecks.md)
