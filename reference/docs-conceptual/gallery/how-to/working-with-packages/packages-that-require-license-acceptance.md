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
# <a name="require-license-acceptance"></a>Exigir a aceitação da licença

O texto Exigir a Aceitação da Licença aparece na página de detalhes do item para módulos que exigem a aceitação da licença. A licença para o módulo pode ser exibida clicando no link **Exibir Licença.txt**.

![Exigir a Aceitação da Licença](media/packages-that-require-license-acceptance/RequireLicenseAcceptance.png)

Usuários receberão uma solicitação para aceitar a licença ao instalar, salvar ou atualizar o módulo por meio do PowerShellGet ou ao implantar a Automação do Azure.

## <a name="require-license-acceptance-on-deploy-to-azure-automation"></a>Exigir a aceitação da licença ao implantar na Automação do Azure

Se o módulo que está sendo implantado na Automação do Azure exigir a aceitação da licença, a interface do usuário do portal exibirá um aviso de isenção informando que "Esse módulo exige a aceitação da licença. Ao clicar em OK, você aceita os termos da licença."

![A implantação na Automação do Azure exige a aceitação da licença](media/packages-that-require-license-acceptance/DeployToAzureAutomationRequireLicenseAcceptanceDisclaimer.png)

## <a name="more-details"></a>Mais detalhes

[Exigir a aceitação da licença no PowerShellGet](../../concepts/module-license-acceptance.md)
[Site da Automação do Azure](/azure/automation)
