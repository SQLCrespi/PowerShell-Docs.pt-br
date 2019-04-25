---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
ms.openlocfilehash: a1e90a0b96f74decb55343292b97befaf1a85f8a
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058107"
---
# <a name="class-based-dsc-resources"></a>Recursos DSC baseados em classe

## <a name="defining-dsc-resources-with-classes"></a>Definindo recursos DSC com classes

Com base nos comentários, tornamos a criação de recursos DSC baseados em classe mais simples e mais fácil de entender.
As principais diferenças entre um recurso DSC baseado em classe e um provedor de recursos DSC de cmdlet são:

* Um arquivo MOF para o esquema não é necessário.
* Uma subpasta **DSCResource** na pasta do módulo não é necessária.
* Um arquivo de módulo do PowerShell pode conter várias classes de recursos DSC.

Para obter mais informações, veja [Escrevendo um recurso personalizado de DSC com classes do PowerShell](https://msdn.microsoft.com/powershell/dsc/authoringresource).
