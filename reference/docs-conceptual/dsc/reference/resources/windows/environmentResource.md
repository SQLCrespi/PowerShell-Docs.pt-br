---
ms.date: 07/16/2020
keywords: DSC,powershell,configuração,instalação
title: Recurso Environment de DSC
ms.openlocfilehash: d8519a66d457767dcbc0e08b01a69a9264997479
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464410"
---
# <a name="dsc-environment-resource"></a>Recurso Environment de DSC

> Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.x

O recurso **Environment** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para gerenciar as variáveis de ambiente do sistema.

## <a name="syntax"></a>Sintaxe

```Syntax
Environment [string] #ResourceName
{
    Name = [string]
    [ Path = [bool] ]
    [ Target = [string] { Process | Machine } ]
    [ Value = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Propriedades

|Propriedade |DESCRIÇÃO |
|---|---|
|Nome |Indica o nome da variável de ambiente para a qual você deseja garantir um estado específico. |
|Caminho |Define a variável de ambiente que está sendo configurada. Defina essa propriedade como `$true` se a variável for **Path**. Caso contrário, defina-a como `$false`. O padrão é `$false`. Se a variável que estiver sendo configurada for a variável **Path**, o valor fornecido por meio da propriedade **Value** será acrescentado ao valor existente. |
|Destino| Indica onde recuperar a variável: O computador ou o processo. Se ambos estiverem indicados, somente o valor do computador será retornado. O padrão é ambos, pois esse é o padrão para o restante do recurso. |
|Valor |O valor que será atribuído à variável de ambiente. |

## <a name="common-properties"></a>Propriedades comuns

|Propriedade |Descrição |
|---|---|
|DependsOn |Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado. Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Indica se existe uma variável. Defina essa propriedade como **Present** para criar a variável de ambiente caso ela não exista ou para garantir que seu valor corresponda ao que é fornecido por meio da propriedade **Value** se a variável já existir. Defina-a como **Absent** para excluir a variável se ela existir. |
|PsDscRunAsCredential |Define a credencial para executar todo o recurso. |

> [!NOTE]
> A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais. Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).

## <a name="example"></a>Exemplo

O exemplo a seguir assegura que TestEnvironmentVariable esteja presente e tenha o valor _TestValue_. Se não estiver presente, será criado.

```powershell
Environment EnvironmentExample
{
    Ensure = "Present"  # You can also set Ensure to "Absent"
    Name = "TestEnvironmentVariable"
    Value = "TestValue"
}
```
