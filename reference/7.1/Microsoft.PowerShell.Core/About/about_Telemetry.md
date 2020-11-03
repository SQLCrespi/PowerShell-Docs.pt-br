---
description: Descreve a telemetria coletada no PowerShell e como recusar.
keywords: powershell
Locale: en-US
ms.date: 08/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_telemetry?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Telemetry
ms.openlocfilehash: ef921d0feefe277c2832c0a459ae150c9a6b4acb
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195919"
---
# <a name="about-telemetry"></a>Sobre a telemetria

## <a name="short-description"></a>DESCRIÇÃO BREVE

Descreve a telemetria coletada no PowerShell e como recusar.

## <a name="long-description"></a>DESCRIÇÃO LONGA

O PowerShell envia dados de telemetria básicos para a Microsoft.
Com esses dados, podemos entender melhor os ambientes nos quais o PowerShell é usado, além de priorizar novos recursos e correções.
Os seguintes pontos de telemetria são registrados:

- Contagem de inícios do PowerShell por tipo (API vs console)
- Contagem de uso exclusivo do PowerShell
- Contagem dos seguintes tipos de execução:
  - Aplicativo (comandos nativos)
  - ExternalScript
  - script
  - Função
  - Cmdlet
- Contagem de recursos experimentais da Microsoft habilitados ou recursos experimentais fornecidos com o PowerShell
- Contagem de sessões hospedadas
- Contagem de módulos de propriedade da Microsoft carregados

Esses dados incluem o nome do sistema operacional, a versão do sistema operacional, a versão do PowerShell e o canal de distribuição.

Para recusar essa telemetria, defina a variável de ambiente POWERSHELL_TELEMETRY_OPTOUT como true, Yes ou 1.

