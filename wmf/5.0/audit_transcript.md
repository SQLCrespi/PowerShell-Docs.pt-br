---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
ms.openlocfilehash: f655cd7aa9b14bd38924d55c8f1246b55ef83756
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085840"
---
# <a name="enhanced-transcription-options"></a>Opções de transcrição avançada

A transcrição do Windows PowerShell foi aperfeiçoada para ser aplicada a todos os aplicativos de hospedagem (como o ISE do Windows PowerShell) em vez de apenas ao host do console (powershell.exe).

Além de se estender para a transcrição, a própria funcionalidade de transcrição foi atualizada para dar suporte ao aninhamento arbitrário de transcrições, metadados adicionais no cabeçalho da transcrição resultante, bem como a definição de um diretório de saída da transcrição (para dar suporte à coleta de log centralizada).

As opções de transcrição (incluindo a habilitação de uma transcrição geral do sistema) podem ser definidas com a configuração **Ativar Transcrição do PowerShell** Política de Grupo (em Modelos Administrativos -> Componentes do Windows -> Windows PowerShell).
