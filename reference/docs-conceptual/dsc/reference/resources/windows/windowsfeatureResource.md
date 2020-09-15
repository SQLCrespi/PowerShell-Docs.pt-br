---
ms.date: 07/16/2020
keywords: DSC,powershell,configuração,instalação
title: Recurso WindowsFeature de DSC
ms.openlocfilehash: b15b267c6898697816b386a381e5a6d59acd492a
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464104"
---
# <a name="dsc-windowsfeature-resource"></a>Recurso WindowsFeature de DSC

> Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.x

O recurso **WindowsFeature** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para garantir que funções e recursos sejam adicionados ou removidos em um nó de destino.

## <a name="syntax"></a>Sintaxe

```Syntax
WindowsFeature [string] #ResourceName
{
    Name = [string]
    [ Credential = [PSCredential] ]
    [ IncludeAllSubFeature = [bool] ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Propriedades

|Propriedade |DESCRIÇÃO |
|---|---|
|Nome |Indica o nome da função ou recurso que você deseja garantir que seja adicionado ou removido. É igual à propriedade **Name** do cmdlet [Get-WindowsFeature](/powershell/module/servermanager/Get-WindowsFeature), não o nome de exibição da função ou recurso. |
|Credencial |Indica as credenciais que devem ser usadas para adicionar ou remover a função ou recurso. |
|IncludeAllSubFeature |Defina essa propriedade como `$true` para garantir o estado de todos os sub-recursos necessários com o estado do recurso especificado com a propriedade **Name**. |
|LogPath |Indica o caminho até um arquivo de log em que você deseja que o provedor de recursos registre a operação. |

## <a name="common-properties"></a>Propriedades comuns

|Propriedade |Descrição |
|---|---|
|DependsOn |Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado. Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Indica se a função ou o recurso foi adicionado. Para garantir que a função ou o recurso sejam adicionados, defina essa propriedade como **Present**. Para garantir que a função ou o recurso sejam removidos, defina essa propriedade como **Absent**. O valor padrão é **Present**. |
|PsDscRunAsCredential |Define a credencial para executar todo o recurso. |

> [!NOTE]
> A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais. Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).

## <a name="example"></a>Exemplo

```powershell
WindowsFeature RoleExample
{
    Ensure = "Present"
    # Alternatively, to ensure the role is uninstalled, set Ensure to "Absent"
    Name = "Web-Server" # Use the Name property from Get-WindowsFeature
}
```
