---
ms.date: 07/17/2020
ms.topic: reference
title: Recurso nxScript de DSC para Linux
description: Recurso nxScript de DSC para Linux
ms.openlocfilehash: c92d7ac76323d39167512734ef743c299857c9a6
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92648810"
---
# <a name="dsc-for-linux-nxscript-resource"></a>Recurso nxScript de DSC para Linux

O recurso **nxScript** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para executar scripts do Linux em um nó do Linux.

## <a name="syntax"></a>Sintaxe

```Syntax
nxScript <string> #ResourceName
{
    GetScript = <string>
    SetScript = <string>
    TestScript = <string>
    [ User = <string> ]
    [ Group = <string> ]
    [ DependsOn = <string[]> ]
}
```

## <a name="properties"></a>Propriedades

|Propriedade |DESCRIÇÃO |
|---|---|
|GetScript |Fornece um script para retornar ao status atual do computador. Esse script é executado quando você invoca o script [GetDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer). O script precisa começar com um shebang, como `#!/bin/bash`. |
|SetScript |Fornece um script que coloca o computador no estado correto. Quando você invoca o script [StartDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer), o **TestScript** é executado primeiro. Se o bloco **TestScript** gerar um código de saída diferente de 0, o bloco **SetScript** será executado. Se o **TestScript** gerar um código de saída igual a 0, o **SetScript** não será executado. O script precisa começar com um shebang, como `#!/bin/bash`. |
|TestScript |Fornece um script que avalia se o nó está atualmente no estado correto. Quando você invoca o script [StartDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer), este script é executado primeiro. Se gerar um código de saída diferente de 0, o **SetScript** será executado. Se gerar um código de saída igual a 0, o **SetScript** não será executado. O **TestScript** também é executado quando você invoca o script [TestDscConfiguration](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer). No entanto, nesse caso, o **SetScript** não será executado, não importa qual código de saída é gerado pelo **TestScript** . O **TestScript** deve ter o conteúdo e deverá gerar um código de saída igual a 0, se a configuração real corresponder à configuração atual de estado desejado, e um código de saída diferente de 0, se não corresponder. A configuração atual de estado desejado é a última configuração aplicada ao nó que está usando o DSC. O script precisa começar com um shebang, como `#!/bin/bash`. |
|Usuário |O usuário com o qual o script será executado. |
|Agrupar |O grupo com o qual o script será executado. |

## <a name="common-properties"></a>Propriedades comuns

|Propriedade |DESCRIÇÃO |
|---|---|
|DependsOn |Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado. Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`. |

## <a name="example"></a>Exemplo

O exemplo a seguir demonstra o uso do recurso **nxScript** para executar um gerenciamento de configuração adicional.

```powershell
Import-DSCResource -Module nx

Node $node
{
    nxScript KeepDirEmpty {

    GetScript = @"
#!/bin/bash
ls /tmp/mydir/ | wc -l
"@

    SetScript = @"
#!/bin/bash
rm -rf /tmp/mydir/*
"@

    TestScript = @'
#!/bin/bash
filecount=`ls /tmp/mydir | wc -l`
if [ $filecount -gt 0 ]
then
    exit 1
else
    exit 0
fi
'@
    }
}
```
