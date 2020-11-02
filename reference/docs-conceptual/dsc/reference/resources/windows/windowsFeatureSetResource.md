---
ms.date: 07/16/2020
ms.topic: reference
title: Recurso do WindowsFeatureSet DSC
description: Recurso do WindowsFeatureSet DSC
ms.openlocfilehash: 327c5e907e9b100f42b6a15684f8b131c1f20a41
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2020
ms.locfileid: "93143068"
---
# <a name="dsc-windowsfeatureset-resource"></a>Recurso do WindowsFeatureSet DSC

> Aplica-se a: Windows PowerShell 5.x

O recurso **WindowsFeatureSet** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para garantir que funções e recursos sejam adicionados ou removidos em um nó de destino. Esse recurso é um [recurso composto](../../../resources/authoringResourceComposite.md) que chama o [recurso WindowsFeature](windowsfeatureResource.md) para cada recurso especificado na propriedade **Name** .

Use esse recurso quando desejar configurar vários Recursos do Windows para o mesmo estado.

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a>Sintaxe

```Syntax
WindowsFeatureSet [string] #ResourceName
{
    Name = [string[]]
    [ Source = [string] ]
    [ IncludeAllSubFeature = [Boolean] ]
    [ Credential = [PSCredential] ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Propriedades

|  Propriedade  |  Descrição   |
|---|---|
|Nome |Os nomes de funções ou recursos que você deseja garantir são adicionados ou removidos. É igual à propriedade **Name** do cmdlet [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature), e não o nome de exibição das funções ou recursos. |
|Fonte |Indica o local do arquivo de origem que deve ser usado para a instalação, se necessário. |
|IncludeAllSubFeature |Defina essa propriedade como `$true` para incluir todos os sub-recursos com os recursos especificados com a propriedade **Name** . |
|Credencial |As credenciais que devem ser usadas para adicionar ou remover as funções ou os recursos. |
|LogPath |O caminho até um arquivo de log em que você deseja que o provedor de recursos registre a operação. |

## <a name="common-properties"></a>Propriedades comuns

|Propriedade |Descrição |
|---|---|
|DependsOn |Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado. Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Indica se as funções ou os recursos são adicionados. Para garantir que as funções e os recursos sejam adicionados, defina essa propriedade como **Present** . Para garantir que as funções e os recursos sejam removidos, defina essa propriedade como **Absent** . O valor padrão é **Present** . |
|PsDscRunAsCredential |Define a credencial para executar todo o recurso. |

> [!NOTE]
> A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais. Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).

## <a name="example"></a>Exemplo

A configuração a seguir garante que os recursos **Servidor Web** (IIS) e **Servidor SMTP** e todos os sub-recursos de cada um sejam instalados.

```powershell
configuration FeatureSetTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {

        WindowsFeatureSet WindowsFeatureSetExample
        {
            Name                    = @("SMTP-Server", "Web-Server")
            Ensure                  = 'Present'
            IncludeAllSubFeature    = $true
        }
    }
}
```
