---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso nxService de DSC para Linux
ms.openlocfilehash: 6bb58796c4deff1153f932f61c328d84f8c4d2ca
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954833"
---
# <a name="dsc-for-linux-nxservice-resource"></a>Recurso nxService de DSC para Linux

O recurso **nxService** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para gerenciar serviços em um nó do Linux.

## <a name="syntax"></a>Sintaxe

```Syntax
nxService <string> #ResourceName
{
    Name = <string>
    [ Controller = <string> { init | upstart | systemd } ]
    [ Enabled = <bool> ]
    [ State = <string> { Running | Stopped } ]
    [ DependsOn = <string[]> ]
}
```

## <a name="properties"></a>Propriedades

|Propriedade |Descrição |
|---|---|
|Nome |O nome do serviço/daemon que será configurado. |
|Controlador |O tipo de controlador de serviço que deve ser usado ao configurar o serviço. |
|Habilitada |Indica se o serviço começa na inicialização. |
|Estado |Indica se o serviço está em execução. Defina essa propriedade como **Stopped** para garantir que o serviço não esteja em execução. Defina-a como **Running** para garantir que o serviço esteja em execução. |

## <a name="common-properties"></a>Propriedades comuns

|Propriedade |Descrição |
|---|---|
|DependsOn |Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado. Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`. |

## <a name="additional-information"></a>Informações adicionais

O recurso **nxService** não criará uma definição de serviço ou um script para o serviço se não existir. É possível usar o recurso **nxFile** de Configuração de Estado Desejado do PowerShell para gerenciar a existência ou o conteúdo do arquivo ou script de definição de serviço.

## <a name="example"></a>Exemplo

O exemplo a seguir mostra a configuração do serviço 'httpd' (para o Apache HTTP Server), registrado com o controlador de serviço **SystemD**.

```powershell
Import-DSCResource -Module nx

Node $node
{
    #Apache Service
    nxService ApacheService {
        Name = 'httpd'
        State = 'running'
        Enabled = $true
        Controller = 'systemd'
    }
}
```