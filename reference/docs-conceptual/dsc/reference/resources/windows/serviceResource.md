---
ms.date: 01/06/2021
ms.topic: reference
title: Recurso Service de DSC
description: Recurso Service de DSC
ms.openlocfilehash: bb151e11475c6e67f1fcb2d73336ff2e34b749b8
ms.sourcegitcommit: afefb3636362857036648c2fe80215bc4e81f5ac
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97957029"
---
# <a name="dsc-service-resource"></a>Recurso Service de DSC

> Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.x

O recurso **Service** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para gerenciar serviços no nó de destino.

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a>Sintaxe

```Syntax
Service [string] #ResourceName
{
    Name = [string]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ Credential = [PSCredential] ]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ State = [string] { Running | Stopped }  ]
    [ Dependencies = [string[]] ]
    [ Description = [string] ]
    [ DisplayName = [string] ]
    [ Path = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Propriedades

|Propriedade |Descrição |
|---|---|
|Nome |Indica o nome do serviço. Observe que, às vezes, é diferente do nome de exibição. É possível obter uma lista dos serviços e seus estados atuais com o cmdlet `Get-Service`. |
|BuiltInAccount |Indica a conta de entrada que deve ser usada para o serviço. Os valores permitidos para essa propriedade são: **LocalService**, **LocalSystem** e **NetworkService**. |
|Credencial |Indica as credenciais para a conta em que o serviço será executado. Essa propriedade e a propriedade **BuiltinAccount** não podem ser usadas juntas. |
|StartupType |Indica o tipo de inicialização para o serviço. Os valores permitidos para essa propriedade são: **Automático**, **Desabilitado** e **Manual**. |
|Estado |Indica o estado que você deseja garantir para o serviço. Os valores são: **Em execução** ou **Parado**. |
|Dependências | Uma matriz dos nomes das dependências que o serviço deve ter. |
|Descrição |Indica a descrição do serviço de destino. |
|DisplayName |Indica o nome de exibição do serviço de destino. |
|Caminho |Indica o caminho para o arquivo binário para um novo serviço. |

## <a name="common-properties"></a>Propriedades comuns

|Propriedade |Descrição |
|---|---|
|DependsOn |Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado. Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Indica se o serviço de destino existe no sistema. Defina essa propriedade como **Ausente** para garantir que o serviço de destino não exista. Defini-la como **Present** garantirá que o serviço de destino exista. O valor padrão é **Present**. |
|PsDscRunAsCredential |Define a credencial para executar todo o recurso. |

> [!NOTE]
> A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais. Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).

## <a name="example"></a>Exemplo

```powershell
configuration ServiceTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {

        Service ServiceExample
        {
            Name        = "TermService"
            StartupType = "Manual"
            State       = "Running"
        }
    }
}
```
