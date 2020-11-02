---
ms.date: 07/16/2020
ms.topic: reference
title: Recurso do ServiceSet DSC
description: Recurso do ServiceSet DSC
ms.openlocfilehash: bcb8382440d80c37179cdc1d1e17376b2511c3f3
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2020
ms.locfileid: "93142949"
---
# <a name="dsc-serviceset-resource"></a>Recurso do ServiceSet DSC

> Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.x

O recurso **ServiceSet** na DSC (Configuração de Estado Desejado) do Windows PowerShell oferece um mecanismo para gerenciar serviços no nó de destino. Esse recurso é um [recurso composto](../../../resources/authoringResourceComposite.md) que chama o [Recurso de serviço](serviceResource.md) para cada serviço especificado na propriedade **Name** .

Use esse recurso quando desejar configurar vários serviços para o mesmo estado.

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a>Sintaxe

```Syntax
ServiceSet [string] #ResourceName
{
    Name = [string[]]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ State = [string] { Running | Stopped }  ]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Propriedades

|Propriedade |Descrição |
|---|---|
|Nome |Indica os nomes do serviço. Observe que, às vezes, isso é diferente dos nomes de exibição. É possível obter uma lista dos serviços e seus estados atuais com o cmdlet `Get-Service`. |
|StartupType |Indica o tipo de inicialização para os serviços. Os valores permitidos para essa propriedade são: **Automático** , **Desabilitado** e **Manual** . |
|BuiltInAccount |Indica a conta de credenciais a ser usada para os serviços. Os valores permitidos para essa propriedade são: **LocalService** , **LocalSystem** e **NetworkService** . |
|Estado |Indica o estado que você deseja garantir para os serviços: **Parado** ou **Em execução** . |
|Credencial |Indica as credenciais para a conta sob a qual o serviço será executado. Essa propriedade e a propriedade **BuiltinAccount** não podem ser usadas juntas. |

## <a name="common-properties"></a>Propriedades comuns

|Propriedade |Descrição |
|---|---|
|DependsOn |Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado. Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Indica se os serviços existem no sistema. Defina essa propriedade como **Ausente** para garantir que os serviços não existam. Defini-la como **Present** garantirá que os serviços de destino existam. O valor padrão é **Present** . |
|PsDscRunAsCredential |Define a credencial para executar todo o recurso. |

> [!NOTE]
> A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais. Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).

## <a name="example"></a>Exemplo

A configuração a seguir inicia os serviços "Áudio do Windows" e "Serviços de Área de Trabalho Remota".

```powershell
configuration ServiceSetTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {
        ServiceSet ServiceSetExample
        {
            Name        = @("TermService", "Audiosrv")
            StartupType = "Manual"
            State       = "Running"
        }
    }
}
```
