---
ms.date: 07/16/2020
ms.topic: reference
title: Recurso Environment de DSC
description: Recurso Environment de DSC
ms.openlocfilehash: c7995fc5e7efdfb9a1dbae3da9f824d33c67085c
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2020
ms.locfileid: "93142575"
---
# <a name="dsc-environment-resource"></a>Recurso Environment de DSC

> Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.x

O recurso **Environment** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para gerenciar as variáveis de ambiente do sistema.

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a>Sintaxe

```Syntax
Environment [string] #ResourceName
{
    Name = [string]
    [ Path = [bool] ]
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
|Caminho |Define a variável de ambiente que está sendo configurada. Defina essa propriedade como `$true` se a variável for **Path** . Caso contrário, defina-a como `$false`. O padrão é `$false`. Se a variável que estiver sendo configurada for a variável **Path** , o valor fornecido por meio da propriedade **Value** será acrescentado ao valor existente. |
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

O exemplo a seguir assegura que TestEnvironmentVariable esteja presente e tenha o valor _TestValue_ . Se não estiver presente, será criado.

```powershell
Environment EnvironmentExample
{
    Ensure = "Present"  # You can also set Ensure to "Absent"
    Name = "TestEnvironmentVariable"
    Value = "TestValue"
}
```
