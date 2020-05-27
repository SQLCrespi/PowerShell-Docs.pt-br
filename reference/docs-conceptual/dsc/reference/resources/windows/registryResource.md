---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso Registry de DSC
ms.openlocfilehash: 9f65815cbe6a94831b88cb3425bf688e1a99a9c0
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83559895"
---
# <a name="dsc-registry-resource"></a>Recurso Registry de DSC

> Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.x

O recurso **Registry** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para gerenciar chaves e valores do registro em um nó de destino.

## <a name="syntax"></a>Sintaxe

```Syntax
Registry [string] #ResourceName
{
    Key = [string]
    ValueName = [string]
    [ Force =  [bool]   ]
    [ Hex = [bool] ]
    [ ValueData = [string[]] ]
    [ ValueType = [string] { Binary | Dword | ExpandString | MultiString | Qword | String }  ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Present | Absent }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Propriedades

|Propriedade |Descrição |
|---|---|
|Chave |Indica o caminho da chave do Registro para o qual você deseja garantir um estado específico. Esse caminho deve incluir o hive. |
|ValueName |Indica o nome do valor de registro. Para adicionar ou remover uma chave do Registro, especifique essa propriedade como uma cadeia de caracteres vazia sem especificar **ValueType** ou **ValueData**. Para modificar ou remover o valor padrão de uma chave do Registro, especifique essa propriedade como uma cadeia de caracteres vazia e também especifique **ValueType** ou **ValueData**. |
|Force |Se a chave do Registro especificada estiver presente, **Force** a substituirá pelo novo valor. Para excluir uma chave do Registro com subchaves, isso deve ser `$true`. |
|Hex |Indica se os dados serão expressos em formato hexadecimal. Se especificado, os dados do valor DWORD/QWORD são apresentados em formato hexadecimal. Não é válido para outros tipos. O valor padrão é `$false`. |
|ValueData |Os dados para o valor de registro. |
|ValueType |Indica o tipo de valor. Há suporte para estes tipos: **Cadeia de caracteres** (REG_SZ), **Binário** (REG-BINARY), **Dword de 32 bits** (REG_DWORD), **Qword de 64 bits** (REG_QWORD), **Cadeia de caracteres múltipla** (REG_MULTI_SZ), **Cadeia de caracteres expansível** (REG_EXPAND_SZ). |

## <a name="common-properties"></a>Propriedades comuns

|Propriedade |Descrição |
|---|---|
|DependsOn |Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado. Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Indica se a chave e o valor existem. Para garantir que existam, defina essa propriedade como **Present**. Para garantir que não existam, defina a propriedade como **Absent**. O valor padrão é **Present**. |
|PsDscRunAsCredential |Define a credencial para executar todo o recurso. |

> [!NOTE]
> A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais. Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).

## <a name="example"></a>Exemplo

Este exemplo assegura que uma chave chamada "ExampleKey" está presente no hive **HKEY\_LOCAL\_MACHINE**.

```powershell
Configuration RegistryTest
{
    Registry RegistryExample
    {
        Ensure      = "Present"  # You can also set Ensure to "Absent"
        Key         = "HKEY_LOCAL_MACHINE\SOFTWARE\ExampleKey"
        ValueName   = "TestValue"
        ValueData   = "TestData"
    }
}
```

> [!NOTE]
> Alterar uma configuração do registro no hive `HKEY_CURRENT_USER` requer que a configuração seja executada com credenciais de usuário, em vez de como o sistema. Você pode usar a propriedade **PsDscRunAsCredential** para especificar credenciais de usuário para a configuração. Por exemplo, veja [Executar DSC com as credenciais do usuário](../../../configurations/runAsUser.md).
