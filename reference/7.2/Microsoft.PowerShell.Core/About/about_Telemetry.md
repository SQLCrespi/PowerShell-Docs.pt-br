---
description: Descreve a telemetria coletada no PowerShell e como recusar.
Locale: en-US
ms.date: 08/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_telemetry?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Telemetry
ms.openlocfilehash: 677d43b405fdc92e6b68d6e903847b11cb671a2c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603559"
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
  - Script
  - Função
  - Cmdlet
- Contagem de recursos experimentais da Microsoft habilitados ou recursos experimentais fornecidos com o PowerShell
- Contagem de sessões hospedadas
- Contagem de módulos de propriedade da Microsoft carregados

Esses dados incluem o nome do sistema operacional, a versão do sistema operacional, a versão do PowerShell e o canal de distribuição.

Para recusar essa telemetria, defina a variável de ambiente POWERSHELL_TELEMETRY_OPTOUT como true, Yes ou 1.

