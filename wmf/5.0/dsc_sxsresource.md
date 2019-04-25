---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
ms.openlocfilehash: 5b31fe833fb0f9d0f3f2733e777e4608a697d583
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62057906"
---
# <a name="side-by-side-module-versioning-support-for-dsc-resources"></a>Suporte ao controle de versão do módulo lado a lado para recursos DSC

Os módulos que contêm recursos DSC podem ser instalados lado a lado, e as configurações DSC podem usar uma versão específica do recurso instalado no sistema.

Para obter mais informações, veja [Usando recursos com várias versões](https://msdn.microsoft.com/powershell/dsc/sxsresource).

## <a name="known-issues"></a>Problemas conhecidos

Nesta versão, os seguintes problemas são problemas conhecidos da instalação lado a lado:

-   Não há suporte para o uso de duas versões diferentes do recurso DSC na mesma configuração.
