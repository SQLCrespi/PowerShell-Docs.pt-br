---
ms.date: 07/17/2020
keywords: DSC,powershell,configuração,instalação
title: Recurso nxPackage de DSC para Linux
ms.openlocfilehash: f61b337f6fbb8e2ea48128642874f050787fc576
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464478"
---
# <a name="dsc-for-linux-nxpackage-resource"></a>Recurso nxPackage de DSC para Linux

O recurso **nxPackage** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para gerenciar pacotes em um nó do Linux.

## <a name="syntax"></a>Sintaxe

```Syntax
nxPackage <string> #ResourceName
{
    Name = <string>
    [ PackageManager = <string> { Yum | Apt | Zypper } ]
    [ PackageGroup = <bool>]
    [ Arguments = <string> ]
    [ ReturnCode = <uint32> ]
    [ FilePath = <string> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present }  ]
}
```

## <a name="properties"></a>Propriedades

|Propriedade |DESCRIÇÃO |
|---|---|
|Nome |O nome do pacote para o qual você deseja garantir um estado específico. |
|PackageManager |Os valores compatíveis são **yum**, **apt** e **zypper**. Especifica o gerenciador de pacotes que deve ser usado ao instalar pacotes. Se **FilePath** for especificado, o caminho fornecido será usado para instalar o pacote. Caso contrário, será usado um Gerenciador de Pacotes para instalar o pacote por meio de um repositório pré-configurado. Se não for fornecido o **PackageManager** ou o **FilePath**, o gerenciador de pacotes padrão para o sistema será usado. |
|PackageGroup |Se for `$true`, o **Name** deverá ser o nome de um grupo de pacotes para usar com um **PackageManager**. **PackageGroup** não é válido quando fornece um **FilePath**. |
|Argumentos |Uma cadeia de caracteres de argumentos que será passada para o pacote exatamente conforme fornecido. |
|ReturnCode |O código de retorno esperado. Se o código de retorno real não corresponder ao valor esperado fornecido aqui, a configuração gerará um erro. |
|FilePath |O caminho do arquivo em que o pacote reside. |

## <a name="common-properties"></a>Propriedades comuns

|Propriedade |DESCRIÇÃO |
|---|---|
|DependsOn |Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado. Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Determina se é necessário verificar se o pacote existe. Defina essa propriedade como **Present** para garantir que o pacote exista. Defina-a como **Absent** para garantir que o pacote não exista. O valor padrão é **Present**. |

## <a name="example"></a>Exemplo

O exemplo a seguir assegura que o pacote denominado "httpd" seja instalado em um computador Linux usando o gerenciador de pacotes "Yum".

```powershell
Import-DSCResource -Module nx

Node $node
{
    nxPackage httpd
    {
        Name = "httpd"
        Ensure = "Present"
        PackageManager = "Yum"
    }
}
```
