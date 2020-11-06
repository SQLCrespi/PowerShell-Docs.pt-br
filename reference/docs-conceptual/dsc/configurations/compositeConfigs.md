---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Aninhar configurações
description: A DSC permite criar configurações compostas aninhando uma configuração dentro de outra.
ms.openlocfilehash: d7a81cb9673126e92e9185aacf19c5c7c17da8ca
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92667412"
---
# <a name="nesting-dsc-configurations"></a>Aninhar configurações do DSC

Uma configuração aninhada (também chamada de configuração composta) é uma configuração chamada de dentro de outra configuração, como se fosse um recurso. Ambas as configurações devem ser definidas no mesmo arquivo.

Vejamos um exemplo simples:

```powershell
Configuration FileConfig
{
    param (
        [Parameter(Mandatory = $true)]
        [String] $CopyFrom,

        [Parameter(Mandatory = $true)]
        [String] $CopyTo
    )

    Import-DscResource -ModuleName PSDesiredStateConfiguration

    File FileTest
    {
        SourcePath = $CopyFrom
        DestinationPath = $CopyTo
        Ensure = 'Present'
    }
}

Configuration NestedFileConfig
{
    Node localhost
    {
        FileConfig NestedConfig
        {
            CopyFrom = 'C:\Test\TestFile.txt'
            CopyTo = 'C:\Test2'
        }
    }
}
```

Neste exemplo, `FileConfig` usa dois parâmetros obrigatórios: **CopyFrom** e **CopyTo** , que são utilizados como valores para as propriedades **SourcePath** e **DestinationPath** no bloco de recursos `File`. A configuração `NestedConfig` chama `FileConfig` como se fosse um recurso. As propriedades do bloco de recursos `NestedConfig` ( **CopyFrom** e **CopyTo** ) são os parâmetros da configuração `FileConfig`.

Atualmente, a DSC não dá suporte a configurações aninhadas em configurações aninhadas. Só é possível aninhar uma configuração com uma camada de profundidade.

## <a name="see-also"></a>Consulte Também

- [Recursos de composição: usando uma configuração DSC como um recurso](../resources/authoringResourceComposite.md)
