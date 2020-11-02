---
ms.date: 07/16/2020
ms.topic: reference
title: Recurso ProcessSet da DSC
description: Recurso ProcessSet da DSC
ms.openlocfilehash: 3e09c8c7b4ca7d8e95b36f9d4c20c2a85abad9dd
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2020
ms.locfileid: "93142558"
---
# <a name="dsc-processset-resource"></a>Recurso ProcessSet da DSC

> Aplica-se a: Windows PowerShell 5.x

O recurso **ProcessSet** na DSC (Configuração de Estado Desejado) do Windows PowerShell fornece um mecanismo para configurar processos em um nó de destino.

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a>Sintaxe

```Syntax
ProcessSet [string] #ResourceName
{
    Path = [string]
    [ Credential = [PSCredential] ]
    [ StandardOutputPath = [string] ]
    [ StandardErrorPath = [string] ]
    [ StandardInputPath = [string] ]
    [ WorkingDirectory = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Propriedades

|Propriedade |Descrição |
|---|---|
|Caminho |O caminho para o executável do processo. Se esses forem os nomes dos arquivos executáveis (caminhos não totalmente qualificados), o recurso DSC pesquisará a variável de ambiente `$env:Path` para localizar os arquivos. Se os valores dessa propriedade forem caminhos totalmente qualificados, o DSC não usará a variável de ambiente `$env:Path` para localizar os arquivos e gerará um erro se qualquer um dos caminhos não existir. Caminhos relativos não são permitidos. |
|Credencial |Indica as credenciais para iniciar o processo. |
|StandardErrorPath |O caminho para o qual os processos gravam o erro padrão. Qualquer arquivo existente será substituído. |
|StandardInputPath |O fluxo do qual o processo recebe entrada padrão. |
|StandardOutputPath |O caminho do arquivo para o qual os processos gravam a saída padrão. Qualquer arquivo existente será substituído. |
|WorkingDirectory |O local usado como diretório de trabalho atual para os processos. |

## <a name="common-properties"></a>Propriedades comuns

|Propriedade |Descrição |
|---|---|
|DependsOn |Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado. Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Especifica se os processos existem. Defina essa propriedade como **Present** para garantir que o processo exista. Caso contrário, defina-a como **Absent** . O valor padrão é **Present** . |
|PsDscRunAsCredential |Define a credencial para executar todo o recurso. |

> [!NOTE]
> A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais. Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).
