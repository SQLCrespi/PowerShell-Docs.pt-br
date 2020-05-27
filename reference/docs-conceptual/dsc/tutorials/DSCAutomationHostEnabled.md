---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Chave do Registro de DSCAutomationHostEnabled
ms.openlocfilehash: 0f35a798e5b7d51fdfb66e4e79ceab0e36ccea5b
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808326"
---
# <a name="dscautomationhostenabled-registry-key"></a>Chave do Registro de DSCAutomationHostEnabled

> Aplica-se a: Windows PowerShell 5.0

O DSC usa a chave de Registro **DSCAutomationHostEnabled** em **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** para habilitar a configuração do computador na inicialização.
O **DSCAutomationHostEnabled** tem suporte para três modos:

|  O valor de DSCAutomationHostEnabled  |  Descrição   |
|---|---|
0 | Desabilite a configuração do computador na inicialização. |
1 | Habilite a configuração do computador na inicialização. |
2 | Habilite a configuração do computador somente se o DSC estiver no estado atual ou pendente. Esse é o valor padrão. |

## <a name="see-also"></a>Consulte Também

Para obter um exemplo de como usar esse recurso para executar as configurações na inicialização inicial, veja [Configurar uma máquina virtual na inicialização inicial usando a DSC](bootstrapDsc.md).
