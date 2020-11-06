---
ms.date: 06/12/2017
title: Exigir a aceitação da licença
description: Como visualizar a licença do pacote na página de detalhes do item
ms.openlocfilehash: 0d8a9ed671f7993726bc3fa41d11159b366e5a28
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92662310"
---
# <a name="require-license-acceptance"></a><span data-ttu-id="23b9e-103">Exigir a aceitação da licença</span><span class="sxs-lookup"><span data-stu-id="23b9e-103">Require license acceptance</span></span>

<span data-ttu-id="23b9e-104">O texto Exigir a Aceitação da Licença aparece na página de detalhes do item para módulos que exigem a aceitação da licença.</span><span class="sxs-lookup"><span data-stu-id="23b9e-104">Require License Acceptance text shows up on item details page for modules that require license acceptance.</span></span> <span data-ttu-id="23b9e-105">A licença para o módulo pode ser exibida clicando no link **Exibir Licença.txt**.</span><span class="sxs-lookup"><span data-stu-id="23b9e-105">License for module can be viewed by clicking on **View License.txt** link.</span></span>

![Exigir a Aceitação da Licença](media/packages-that-require-license-acceptance/RequireLicenseAcceptance.png)

<span data-ttu-id="23b9e-107">Usuários receberão uma solicitação para aceitar a licença ao instalar, salvar ou atualizar o módulo por meio do PowerShellGet ou ao implantar a Automação do Azure.</span><span class="sxs-lookup"><span data-stu-id="23b9e-107">Users will be prompted to accept the license when installing, saving or updating the module through PowerShellGet or when deploying to Azure Automation.</span></span>

## <a name="require-license-acceptance-on-deploy-to-azure-automation"></a><span data-ttu-id="23b9e-108">Exigir a aceitação da licença ao implantar na Automação do Azure</span><span class="sxs-lookup"><span data-stu-id="23b9e-108">Require License Acceptance on Deploy to Azure Automation</span></span>

<span data-ttu-id="23b9e-109">Se o módulo que está sendo implantado na Automação do Azure exigir a aceitação da licença, a interface do usuário do portal exibirá um aviso de isenção informando que "Esse módulo exige a aceitação da licença.</span><span class="sxs-lookup"><span data-stu-id="23b9e-109">If the module being deployed to Azure Automation requires license acceptance, portal UI will show a disclaimer saying 'This module requires license acceptance.</span></span> <span data-ttu-id="23b9e-110">Ao clicar em OK, você aceita os termos da licença."</span><span class="sxs-lookup"><span data-stu-id="23b9e-110">By clicking OK, you are accepting license terms.'</span></span>

![A implantação na Automação do Azure exige a aceitação da licença](media/packages-that-require-license-acceptance/DeployToAzureAutomationRequireLicenseAcceptanceDisclaimer.png)

## <a name="more-details"></a><span data-ttu-id="23b9e-112">Mais detalhes</span><span class="sxs-lookup"><span data-stu-id="23b9e-112">More details</span></span>

<span data-ttu-id="23b9e-113">[Exigir a aceitação da licença no PowerShellGet](../../concepts/module-license-acceptance.md)
[Site da Automação do Azure](/azure/automation)</span><span class="sxs-lookup"><span data-stu-id="23b9e-113">[Require License Acceptance in PowerShellGet](../../concepts/module-license-acceptance.md)
[Azure Automation website](/azure/automation)</span></span>
