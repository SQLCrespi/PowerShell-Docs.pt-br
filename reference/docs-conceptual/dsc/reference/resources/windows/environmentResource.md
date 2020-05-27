---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso Environment de DSC
ms.openlocfilehash: 5670646b6e94019f436d85296deff4de8da920f6
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560348"
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
|Valor |O valor que será atribuído à variável de ambiente. |

## <a name="common-properties"></a>Propriedades comuns

|Propriedade |DESCRIÇÃO |
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
