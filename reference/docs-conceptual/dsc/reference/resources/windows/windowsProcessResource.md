---
ms.date: 07/16/2020
ms.topic: reference
title: Recurso WindowsProcess de DSC
description: Recurso WindowsProcess de DSC
ms.openlocfilehash: 3076e9cb857b78953c164253351b23e7da9b40c6
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2020
ms.locfileid: "93143000"
---
# <a name="dsc-windowsprocess-resource"></a>Recurso WindowsProcess de DSC

> Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.x

O recurso **WindowsProcess** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para configurar processos em um nó de destino.

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a>Sintaxe

```Syntax
WindowsProcess [string] #ResourceName
{
    Arguments = [string]
    Path = [string]
    [ Credential = [PSCredential] ]
    [ StandardErrorPath = [string] ]
    [ StandardInputPath = [string] ]
    [ StandardOutputPath = [string] ]
    [ WorkingDirectory = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Propriedades

|Propriedade |DESCRIÇÃO |
|---|---|
|Argumentos |Indica uma cadeia de caracteres de argumentos para passar para o processo no estado em que se encontra. Se você precisar passar vários argumentos, coloque todos nessa cadeia de caracteres. |
|Caminho |O caminho para o executável do processo. Se esse for o nome do arquivo do executável (não o caminho totalmente qualificado), o recurso DSC pesquisará a variável de ambiente `$env:Path` para localizar o arquivo executável. Se o valor dessa propriedade for um caminho totalmente qualificado, o DSC não usará a variável de ambiente `$env:Path` para localizar o arquivo e emitirá um erro se o caminho não existir. Caminhos relativos não são permitidos. |
|Credencial |Indica as credenciais para iniciar o processo. |
|StandardErrorPath |Indica o caminho do diretório para escrever o erro padrão. Qualquer arquivo existente será substituído. |
|StandardInputPath |Indica o local de entrada padrão. |
|StandardOutputPath |Indica o local para escrever a saída padrão. Qualquer arquivo existente será substituído. |
|WorkingDirectory |Indica o local que será usado como diretório de trabalho atual para o processo. |

## <a name="common-properties"></a>Propriedades comuns

|Propriedade |DESCRIÇÃO |
|---|---|
|DependsOn |Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado. Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Indica se o processo existe. Defina essa propriedade como **Present** para garantir que o processo exista. Caso contrário, defina-a como **Absent** . O valor padrão é **Present** . |
|PsDscRunAsCredential |Define a credencial para executar todo o recurso. |
