---
ms.date: 06/12/2017
title: Implantar na Automação do Azure
description: Este artigo descreve como usar a Galeria do PowerShell para implantar um pacote para a Automação do Azure.
ms.openlocfilehash: e9de079ee6cc950c8a268423b9eabd515959b718
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92662363"
---
# <a name="deploy-to-azure-automation"></a>Implantar na Automação do Azure

O botão Implantar na Automação do Azure na página de detalhes do pacote implantará o pacote da Galeria do PowerShell para a Automação do Azure.

![Botão Implantar na Automação do Azure](media/deploy-to-azure-automation/DeployToAzureAutomationButton.png)

Quando acionado, ele redirecionará você para o Portal de Gerenciamento do Azure, em que você entra usando as credenciais de sua conta do Azure. Se o pacote incluir dependências, todas as dependências serão implantadas também na Automação do Azure.

> [!WARNING]
> Se o mesmo pacote com a mesma versão já existir na sua conta de Automação, implantá-lo novamente por meio da Galeria do PowerShell substituirá o pacote na conta de Automação.

Se você implantar um módulo, ele será exibido na seção Módulos da Automação do Azure. Se você implantar um script, ele será exibido na seção Runbooks da Automação do Azure.

O botão Implantar na Automação do Azure pode ser desabilitado, adicionando a marca AzureAutomationNotSupported aos metadados do pacote.

## <a name="require-license-acceptance-on-deploy-to-azure-automation"></a>Exigir a aceitação da licença ao implantar na Automação do Azure

Se o módulo que está sendo implantado na Automação do Azure exigir a aceitação da licença, a interface do usuário do portal exibirá um aviso de isenção informando que "Esse módulo exige a aceitação da licença. Ao clicar em OK, você aceita os termos da licença."

![A implantação na Automação do Azure exige a aceitação da licença](media/deploy-to-azure-automation/DeployToAzureAutomationRequireLicenseAcceptanceDisclaimer.png)

## <a name="more-details"></a>Mais detalhes

- [Exigir a aceitação da licença no PowerShellGet](../../concepts/module-license-acceptance.md)
- [Exigir a aceitação da licença na Galeria do PowerShell](packages-that-require-license-acceptance.md)
- [Site da Automação do Azure](https://azure.microsoft.com/services/automation/)
