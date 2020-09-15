---
ms.date: 07/17/2020
keywords: DSC,powershell,configuração,instalação
title: Recurso nxGroup de DSC para Linux
ms.openlocfilehash: f196c74b94ec27818d58b59d1e489facd8ab0a65
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464427"
---
# <a name="dsc-for-linux-nxgroup-resource"></a>Recurso nxGroup de DSC para Linux

O recurso **nxGroup** na Configuração de Estado Desejado (DSC) do PowerShell fornece um mecanismo para gerenciar grupos locais em um nó do Linux.

## <a name="syntax"></a>Sintaxe

```Syntax
nxGroup <string> #ResourceName
{
    GroupName = <string>
    [ Members = <string[]> ]
    [ MembersToInclude = <string[]> ]
    [ MembersToExclude = <string[]> ]
    [ PreferredGroupID = <string> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present } ]
}
```

## <a name="properties"></a>Propriedades

|Propriedade |DESCRIÇÃO |
|---|---|
|GroupName |Especifica o nome do grupo para o qual você deseja garantir um estado específico. |
|Membros |Especifica os membros que formam o grupo. |
|MembersToInclude |Especifica os usuários que você deseja garantir que sejam membros do grupo. |
|MembersToExclude |Especifica os usuários que você deseja garantir que não sejam membros do grupo. |
|PreferredGroupID |Define a ID do grupo para o valor fornecido, se possível. Se a ID do grupo estiver em uso no momento, a próxima ID de grupo disponível será usada. |

## <a name="common-properties"></a>Propriedades comuns

|Propriedade |DESCRIÇÃO |
|---|---|
|DependsOn |Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado. Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Determina se é necessário verificar se o grupo existe. Defina essa propriedade como **Present** para garantir que o grupo exista. Defina-a como **Absent** para garantir que o grupo não exista. O valor padrão é **Present**. |

## <a name="example"></a>Exemplo

O exemplo a seguir garante que o usuário 'monuser' exista e seja membro do grupo 'DBusers'.

```powershell
Import-DSCResource -Module nx

Node $node
{
    nxUser UserExample {
       UserName = 'monuser'
       Description = 'Monitoring user'
       Password = '$6$fZAne/Qc$MZejMrOxDK0ogv9SLiBP5J5qZFBvXLnDu8HY1Oy7ycX.Y3C7mGPUfeQy3A82ev3zIabhDQnj2ayeuGn02CqE/0'
       Ensure = 'Present'
       HomeDirectory = '/home/monuser'
    }

    nxGroup GroupExample {
       GroupName = 'DBusers'
       Ensure = 'Present'
       MembersToInclude = 'monuser'
       DependsOn = '[nxUser]UserExample'
    }
}
```
