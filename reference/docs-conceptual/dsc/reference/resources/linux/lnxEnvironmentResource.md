---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso nxEnvironment de DSC para Linux
ms.openlocfilehash: 55c1b2402e23c1042ed48b40c1084aa63c515b36
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953223"
---
# <a name="dsc-for-linux-nxenvironment-resource"></a>Recurso nxEnvironment de DSC para Linux

O recurso **nxEnvironment** na Configuração de Estado Desejado (DSC) do PowerShell fornece um mecanismo para gerenciar as variáveis de ambiente do sistema em um nó do Linux.

## <a name="syntax"></a>Sintaxe

```Syntax
nxEnvironment <string> #ResourceName
{
    Name = <string>
    [ Value = <string>
    [ Path = <bool> }
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present }  ]
}
```

## <a name="properties"></a>Propriedades

|Propriedade |Descrição |
|---|---|
|Nome |Indica o nome da variável de ambiente para a qual você deseja garantir um estado específico. |
|Valor |O valor que será atribuído à variável de ambiente. |
|Caminho |Define a variável de ambiente que está sendo configurada. Defina essa propriedade como `$true` se a variável for **Path**. Caso contrário, defina-a como `$false`. O padrão é `$false`. Se a variável que estiver sendo configurada for a variável **Path**, o valor fornecido por meio da propriedade **Value** será acrescentado ao valor existente. |

## <a name="common-properties"></a>Propriedades comuns

|Propriedade |Descrição |
|---|---|
|DependsOn |Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado. Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Determina se é necessário verificar se a variável existe. Defina essa propriedade como **Present** para garantir que a variável exista. Defina-a como **Absent** para garantir que a variável não exista. O valor padrão é **Present**. |

## <a name="additional-information"></a>Informações adicionais

- Se **Path** estiver ausente ou definido como `$false`, as variáveis de ambiente serão gerenciadas em `/etc/environment`.
  Seus programas ou scripts poderão exigir uma configuração para fornecer o arquivo `/etc/environment` para acessar as variáveis de ambiente gerenciadas.
- Se **Path** estiver definido como `$true`, a variável de ambiente será gerenciada no arquivo `/etc/profile.d/DSCenvironment.sh`. Esse arquivo será criado se não existir. Se **Ensure** estiver definido como **Absent** e **Path** estiver definido como `$true`, uma variável de ambiente existente será removida somente de `/etc/profile.d/DSCenvironment.sh`, e não de outros arquivos.

## <a name="example"></a>Exemplo

O exemplo a seguir mostra como usar o recurso **nxEnvironment** para garantir que **TestEnvironmentVariable** esteja presente e tenha o valor "Test-Value". Se **TestEnvironmentVariable** não estiver presente, será criado.

```powershell
Import-DSCResource -Module nx

nxEnvironment EnvironmentExample
{
    Ensure = "Present"
    Name = "TestEnvironmentVariable"
    Value = "TestValue"
}
```