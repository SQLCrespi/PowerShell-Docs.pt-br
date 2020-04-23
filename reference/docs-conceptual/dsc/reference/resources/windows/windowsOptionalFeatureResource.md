---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso do WindowsOptionalFeature DSC
ms.openlocfilehash: 7312edcaeb47427bf4736f466a9ed41bd7c31f6a
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "71954643"
---
# <a name="dsc-windowsoptionalfeature-resource"></a>Recurso do WindowsOptionalFeature DSC

> Aplica-se a: Windows PowerShell 5.x

O recurso **WindowsOptionalFeature** na DSC (Configuração de Estado Desejado) do Windows PowerShell oferece um mecanismo para garantir que os recursos opcionais sejam habilitados em um nó de destino.

## <a name="syntax"></a>Sintaxe

```Syntax
WindowsOptionalFeature [string] #ResourceName
{
    Name = [string]
    [ Source = [string[]] ]
    [ NoWindowsUpdateCheck = [bool] ]
    [ RemoveFilesOnDisable = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Enable | Disable }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Propriedades

|Propriedade |Descrição |
|---|---|
|Nome |Indica o nome do recurso que você deseja garantir que esteja habilitado ou desabilitado. |
|Fonte |Não implementado. |
|NoWindowsUpdateCheck |Especifica se o DISM contata o WU (Windows Update) ao procurar os arquivos de origem para habilitar um recurso. Se `$true`, o DISM não contatará o WU. |
|RemoveFilesOnDisable |Definido como `$true` para remover todos os arquivos associados ao recurso quando **Ensure** estiver definido como **Absent**. |
|LogLevel |O nível máximo de saída mostrado nos logs. Os valores aceitos são: **ErrorsOnly**, **ErrorsAndWarning** e **ErrorsAndWarningAndInformation**. |
|LogPath |O caminho até um arquivo de log em que você deseja que o provedor de recursos registre a operação. |

## <a name="common-properties"></a>Propriedades comuns

|Propriedade |Descrição |
|---|---|
|DependsOn |Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado. Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Especifica se o recurso está habilitado. Para garantir que o recurso seja habilitado, defina essa propriedade como _Enable_. Para garantir que o recurso seja desabilitado, defina essa propriedade como _Disable_. O valor padrão é _Enable_. |
|PsDscRunAsCredential |Define a credencial para executar todo o recurso. |

> [!NOTE]
> A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais. Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).