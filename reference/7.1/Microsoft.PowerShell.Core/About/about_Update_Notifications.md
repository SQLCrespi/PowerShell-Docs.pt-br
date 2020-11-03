---
description: Notifica os usuários sobre a inicialização do PowerShell que uma nova versão do PowerShell foi lançada.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_update_notifications?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Update_Notifications
ms.openlocfilehash: 258eb9316ba063069d032bc115bdeb4614666f37
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196379"
---
# <a name="about-update-notifications"></a>Sobre notificações de atualização

## <a name="short-description"></a>DESCRIÇÃO BREVE

Notifica os usuários sobre a inicialização do PowerShell que uma nova versão do PowerShell foi lançada.

## <a name="long-description"></a>DESCRIÇÃO LONGA

A partir do PowerShell 7,0, o PowerShell usa notificações de atualização para alertar os usuários sobre a existência de atualizações para o PowerShell. Uma vez por dia, o PowerShell consulta um serviço online para determinar se uma versão mais recente está disponível.

> [!NOTE]
> Enquanto a verificação de atualização ocorre durante a primeira sessão em um determinado período de 24 horas, por motivos de desempenho, a notificação só será mostrada no início das sessões subsequentes. Além disso, por motivos de desempenho, a verificação não será iniciada até pelo menos 3 segundos após o início da sessão.

Por padrão, o PowerShell assina um dos dois canais de notificação diferentes dependendo de sua versão/branch. As versões GA (em disponibilidade geral) com suporte do PowerShell retornam apenas notificações para versões GA atualizadas. As versões RC (Release Candidate) e Versão prévia notificam atualizações para RC, GA e versão prévia.

O comportamento da notificação de atualização pode ser alterado usando a variável de ambiente `POWERSHELL_UPDATECHECK`. Os seguintes valores têm suporte:

- `Off` desativa o recurso de notificação de atualização
- `Default` é o mesmo que não definir `POWERSHELL_UPDATECHECK` :
  - As versões GA notificam atualizações de versões GA
  - As versões RC/Versão prévia notificam atualizações de GA e versão prévia
- `LTS` Notifica apenas sobre atualizações de versões GA de manutenção de longo prazo (LTS)

Os pontos de extremidade a seguir são usados no momento para determinar a versão mais recente de cada canal:

- `LTS`: https://aka.ms/pwsh-buildinfo-lts
- `Stable`: https://aka.ms/pwsh-buildinfo-stable
- `Preview`: https://aka.ms/pwsh-buildinfo-preview

A notificação de atualização não fornece nenhuma maneira de atualizar automaticamente o PowerShell. No futuro, pode haver mais instruções ou recursos para atualizar de dentro do PowerShell, mas hoje em dia, você deve usar o mesmo mecanismo de instalação usado para instalar o PowerShell para atualizá-lo.

