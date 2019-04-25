---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
ms.openlocfilehash: 57152e9f62c34600df63a2db8e9683928e825d93
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085789"
---
# <a name="detailed-information-about-lcm-state"></a>Informações detalhadas sobre o estado do LCM

Fizemos melhorias na exposição de detalhes sobre o estado do LCM. O LCMState retornado por Get-DscLocalConfigurationManager agora pode conter os seguintes valores:

* **Idle**
* **Busy**
* **PendingReboot**
* **PendingConfiguration**

Também adicionamos uma propriedade de LCMStateDetail que contém mais informações sobre o estado.
