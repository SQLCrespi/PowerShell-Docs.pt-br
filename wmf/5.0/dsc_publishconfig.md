---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
ms.openlocfilehash: db4543b788ad0a5c7aa32706246446533b901d09
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085806"
---
# <a name="deliver-a-configuration-document-without-applying"></a>Entregar um documento de configuração sem aplicação

O cmdlet [Publish-DscConfiguration](https://technet.microsoft.com/library/mt517875.aspx) faz uma cópia de um arquivo MOF de configuração e a cola em um nó de destino, mas não aplica a configuração.
Essa configuração é aplicada durante a próxima passagem de consistência ou ao executar o cmdlet [Update-DscConfiguration](https://technet.microsoft.com/library/mt143541.aspx).
