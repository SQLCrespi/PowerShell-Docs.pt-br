---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso de DSC WindowsPackageCab
ms.openlocfilehash: 1b1b8b6d065882400608d26a991318fec9ad5747
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83563942"
---
# <a name="dsc-windowspackagecab-resource"></a>Recurso de DSC WindowsPackageCab

> Aplica-se a: Windows PowerShell 5.1

O **WindowsPackageCab** no DSC (Desired State Configuration) do Windows PowerShell fornece um mecanismo para instalar ou desinstalar pacotes de gabinete (.cab) do Windows em um nó de destino.

O nó de destino deve ter o módulo PowerShell do DISM instalado. Para obter informações, consulte [Usar DISM no Windows PowerShell](/windows-hardware/manufacture/desktop/use-dism-in-windows-powershell-s14).

## <a name="syntax"></a>Sintaxe

```Syntax
{
    Name = [string]
    SourcePath = [string]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    Ensure = [string] { Absent | Present }
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Propriedades

|Propriedade |Descrição |
|---|---|
|Nome |Indica o nome do pacote para o qual você deseja garantir um estado específico. |
|SourcePath |Indica o caminho em que o pacote reside. |
|LogPath |Indica o caminho completo em que você deseja que o provedor salve um arquivo de log para instalar ou desinstalar o pacote. |

## <a name="common-properties"></a>Propriedades comuns

|Propriedade |Descrição |
|---|---|
|DependsOn |Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado. Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Indica se o pacote foi instalado. Defina esta propriedade como **Absent** para garantir que o pacote não seja instalado (ou desinstalar o pacote, se ele estiver instalado). Defina-a como **Present** para garantir que o pacote seja instalado. **Ensure** é uma propriedade obrigatória no recurso **WindowsPackageCab**. |
|PsDscRunAsCredential |Define a credencial para executar todo o recurso. |

## <a name="example"></a>Exemplo

A configuração de exemplo a seguir usa parâmetros de entrada e garante que o arquivo .cab especificado pelo parâmetro `$Name` esteja instalado.

```powershell
Configuration Sample_WindowsPackageCab
{
    param
    (
        [Parameter (Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $Name,

        [Parameter (Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $SourcePath,

        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $LogPath
    )

    Import-DscResource -ModuleName 'PSDscResources'

    WindowsPackageCab WindowsPackageCab1
    {
        Name = $Name
        Ensure = 'Present'
        SourcePath = $SourcePath
        LogPath = $LogPath
    }
}
```
