---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso do WindowsOptionalFeatureSet DSC
ms.openlocfilehash: 0930bd0c6d1955005ea607b610e004818c0ad06f
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560144"
---
# <a name="dsc-windowsoptionalfeatureset-resource"></a>Recurso do WindowsOptionalFeatureSet DSC

> Aplica-se a: Windows PowerShell 5.x

O recurso **WindowsOptionalFeatureSet** na DSC (Configuração de Estado Desejado) do Windows PowerShell oferece um mecanismo para garantir que os recursos opcionais sejam habilitados em um nó de destino. Esse recurso é um [recurso composto](../../../resources/authoringResourceComposite.md) que chama o [recurso WindowsOptionalFeature](windowsOptionalFeatureResource.md) para cada recurso especificado na propriedade **Name**.

Use esse recurso quando desejar configurar vários recursos opcionais do Windows para o mesmo estado.

## <a name="syntax"></a>Sintaxe

```Syntax
WindowsOptionalFeatureSet [string] #ResourceName
{
    Name = [string[]]
    [ Source = [string] ]
    [ RemoveFilesOnDisable = [bool] ]
    [ LogPath = [string] ]
    [ NoWindowsUpdateCheck = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Enable | Disable }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Propriedades

|Propriedade |Descrição |
|---|---|
|Nome |Indica o nome dos recursos que você deseja garantir que estejam habilitados ou desabilitados. |
|Fonte |Não implementado. |
|NoWindowsUpdateCheck |Especifica se o DISM contata o WU (Windows Update) ao procurar os arquivos de origem para habilitar recursos. Se `$true`, o DISM não contatará o WU. |
|RemoveFilesOnDisable |Definido como `$true` para remover todos os arquivos associados aos recursos quando **Ensure** está definido como **Absent**. |
|LogLevel |O nível máximo de saída mostrado nos logs. Os valores aceitos são: **ErrorsOnly**, **ErrorsAndWarning** e **ErrorsAndWarningAndInformation**. |
|LogPath |O caminho até um arquivo de log em que você deseja que o provedor de recursos registre a operação. |

## <a name="common-properties"></a>Propriedades comuns

|Propriedade |Descrição |
|---|---|
|DependsOn |Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado. Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Especifica se os recursos estão habilitados. Para garantir que os recursos sejam habilitados, defina essa propriedade como **Enable**. Para garantir que os recursos sejam desabilitados, defina essa propriedade como **Disable**. O valor padrão é **Enable**. |
|PsDscRunAsCredential |Define a credencial para executar todo o recurso. |

> [!NOTE]
> A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais. Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).
