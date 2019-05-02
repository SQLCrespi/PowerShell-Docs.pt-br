---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
ms.openlocfilehash: 31fde15e644455dbe77f68bca713bf026544fdc7
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62057563"
---
# <a name="on-demand-pull-of-dsc-configurations"></a>PULL sob demanda de configurações DSC

O novo cmdlet Update-DscConfiguration dispara um pull do(s) servidor(es) de recepção definido(s) na metaconfiguração. Em geral, esse comportamento é conhecido como “Pull agora”.


Depois de disparado, o pull se comporta exatamente como faria quando disparado durante a frequência regular:

1. A soma de verificação da configuração atual é comparada com a soma de verificação da configuração no servidor de recepção.
2. Se elas forem iguais, ele será concluído com êxito sem aplicar a configuração.
3. Se forem diferentes, a configuração será movida para baixo do servidor de recepção e aplicada.

**Observação:** se RefreshMode = “Push” para a Metaconfiguração, este cmdlet retorna um erro; portanto, esse cmdlet nunca executará nenhuma ação quando um nó de destino estiver no modo “Push”.

```powershell
Update-DscConfiguration     [[-ComputerName] <string[]>]
                            [-Wait]
                            [-Force]
                            [-JobName <string>]
                            [-Credential<pscredential>]
                            [-ThrottleLimit <int>]
                            [-WhatIf]
                            [-Confirm]
                            [<CommonParameters>]

Update-DscConfiguration     -CimSession <CimSession[]>
                            [-Wait]
                            [-Force]
                            [-JobName <string>]
                            [-ThrottleLimit <int>]
                            [-WhatIf]
                            [-Confirm]
                            [<CommonParameters>]
```
