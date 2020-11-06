---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Chave do Registro de DSCAutomationHostEnabled
description: Este artigo define os valores que podem ser definidos na chave do Registro DSCAutomationHostEnabled
ms.openlocfilehash: 50f752dd882e9b0787ed4a4cbc22731fc1d608f5
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656179"
---
# <a name="dscautomationhostenabled-registry-key"></a>Chave do Registro de DSCAutomationHostEnabled

> Aplica-se a: Windows PowerShell 5.0

O DSC usa a chave de Registro **DSCAutomationHostEnabled** em **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** para habilitar a configuração do computador na inicialização. O **DSCAutomationHostEnabled** tem suporte para três modos:

| O valor de DSCAutomationHostEnabled |                                              Descrição                                              |
| ------------------------------ | ----------------------------------------------------------------------------------------------------- |
| 0                              | Desabilite a configuração do computador na inicialização.                                                           |
| 1                              | Habilite a configuração do computador na inicialização.                                                            |
| 2                              | Habilite a configuração do computador somente se o DSC estiver no estado atual ou pendente. Esse é o valor padrão. |

## <a name="see-also"></a>Consulte Também

Para obter um exemplo de como usar esse recurso para executar as configurações na inicialização inicial, veja [Configurar uma máquina virtual na inicialização inicial usando a DSC](bootstrapDsc.md).
