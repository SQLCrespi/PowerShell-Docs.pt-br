---
ms.date: 07/16/2020
ms.topic: reference
title: Recursos File de DSC
description: Recursos File de DSC
ms.openlocfilehash: b62b9b80beb1f433715b32b41445dd0a8bb19d84
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2020
ms.locfileid: "93142932"
---
# <a name="dsc-file-resource"></a>Recursos File de DSC

> Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.x

O recurso **File** no DSC (Desired State Configuration) do Windows PowerShell fornece um mecanismo para gerenciar arquivos e pastas no nó de destino. O **DestinationPath** e o **SourcePath** devem ser acessíveis pelo nó de destino.

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a>Sintaxe

```Syntax
File [string] #ResourceName
{
    DestinationPath = [string]
    [ Attributes = [string[]] { Archive | Hidden | ReadOnly | System }]
    [ Checksum = [string] { CreatedDate | ModifiedDate | SHA-1 | SHA-256 | SHA-512 } ]
    [ Contents = [string] ]
    [ Credential = [PSCredential] ]
    [ Force = [bool] ]
    [ Recurse = [bool] ]
    [ SourcePath = [string] ]
    [ Type = [string] { Directory | File } ]
    [ MatchSource = [bool] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Propriedades

|Propriedade |Descrição |
|---|---|
|DestinationPath |O local, no nó de destino, que você quer que seja **Present** ou **Absent** com **Ensure** . |
|Atributos |O estado desejado dos atributos para o arquivo ou diretório de destino. Os valores válidos são _Archive_ , _Hidden_ , _ReadOnly_ e _System_ . |
|Checksum (soma de verificação) |O tipo de soma de verificação a usar para determinar se dois arquivos são iguais. Os valores válidos incluem: **SHA-1** , **SHA-256** , **SHA-512** , **createdDate** , **modifiedDate** . |
|Conteúdo |Válido apenas quando usado com o **Type** **File** . Indica se o conteúdo a **Ensure** está **Present** ou **Absent** no arquivo de destino. |
|Credencial |As credenciais necessárias para acessar recursos, como arquivos de origem. |
|Force |Substitui as operações de acesso que resultariam em erro (como substituir um arquivo ou excluir um diretório que não esteja vazio). O valor padrão é `$false`. |
|Recurse |Válido apenas quando usado com o **Type** **Directory** . Executa a operação de estado recursivamente para todo o conteúdo do diretório, subdiretórios e conteúdo de subdiretório. O valor padrão é `$false`. |
|SourcePath |O caminho do qual o recurso de arquivo ou pasta deve ser copiado. |
|Type |O tipo de recurso que está sendo configurado. Os valores válidos são **Directory** e **File** . O valor padrão é **File** . |
|MatchSource |Determina se o recurso deve monitorar novos arquivos adicionados ao diretório de origem após a cópia inicial. Um valor `$true` indica que, após a cópia inicial, os novos arquivos de origem devem ser copiados para o destino. Se for definido como `$false`, o recurso armazena em cache o conteúdo do diretório de origem e ignora todos os arquivos adicionados após a cópia inicial. O valor padrão é `$false`. |

> [!WARNING]
> Se você não especificar um valor para **Credential** ou **PSRunAsCredential** , o recurso usará a conta de computador do nó de destino para acessar o **SourcePath** . Quando o **SourcePath** é um compartilhamento UNC, isso pode resultar em um erro "Acesso negado". Verifique se suas permissões estão definidas adequadamente ou use as propriedades **Credential** ou **PSRunAsCredential** para especificar a conta que deve ser usada.

## <a name="common-properties"></a>Propriedades comuns

|Propriedade |Descrição |
|---|---|
|DependsOn |Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado. Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Determina se o arquivo e **Contents** em **Destination** devem existir ou não. Defina essa propriedade como **Present** para garantir que o arquivo exista. Defina-a como **Absent** para garantir que não exista. O valor padrão é **Present** . |
|PsDscRunAsCredential |Define a credencial para executar todo o recurso. |

> [!NOTE]
> A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais. Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).

### <a name="additional-information"></a>Informações adicionais

- Ao especificar apenas um **DestinationPath** , o recurso garante que o caminho existe caso seja **Present** ou se não existe caso seja **Absent** .
- Quando você especifica um **SourcePath** e um **DestinationPath** com um valor **Type** do **Diretório** , o recurso copia o diretório de origem para o caminho de destino. As propriedades **Recurse** , **Force** e **MatchSource** alteram o tipo de operação de cópia executada, embora **Credential** determine qual conta usar para acessar o diretório de origem.
- Se você não definir a propriedade **Recurse** como `$true` ao copiar um diretório, nenhum dos conteúdos do diretório existente será copiado. Somente o diretório especificado será copiado.
- Se você tiver especificado um valor de **ReadOnly** para a propriedade **Attributes** junto com um **DestinationPath** , **Ensure** **Present** criarão o caminho especificado, enquanto **Contents** definirá o conteúdo do arquivo. Uma configuração **Ensure** **Absent** ignoraria a propriedade **Attributes** completamente e removeria qualquer arquivo no caminho especificado.

## <a name="example"></a>Exemplo

O exemplo a seguir copia um diretório e seus subdiretórios de um servidor de pull para um nó de destino usando o recurso de arquivo. Se a operação for bem-sucedida, o recurso de Log gravará uma mensagem de confirmação no log de eventos.

O diretório de origem é um caminho UNC (`\\PullServer\DemoSource`) compartilhado do servidor de pull. A propriedade **Recurse** garante que todos os subdiretórios também sejam copiados.

> [!IMPORTANT]
> O LCM no nó de destino é executado no contexto da conta do sistema local por padrão. Para conceder acesso ao **SourcePath** , dê à conta do computador do nó de destino as permissões apropriadas. **Credential** e **PSDSCRunAsCredential** alteram o contexto que o LCM usa para acessar o **SourcePath** . Você ainda precisa conceder acesso à conta a ser usada para acessar o **SourcePath** .

```powershell
Configuration FileResourceDemo
{
    Node "localhost"
    {
        File DirectoryCopy
        {
            Ensure = "Present" # Ensure the directory is Present on the target node.
            Type = "Directory" # The default is File.
            Recurse = $true # Recursively copy all subdirectories.
            SourcePath = "\\PullServer\DemoSource"
            DestinationPath = "C:\Users\Public\Documents\DSCDemo\DemoDestination"
        }

        Log AfterDirectoryCopy
        {
            # The message below gets written to the Microsoft-Windows-Desired State Configuration/Analytic log
            Message = "Finished running the file resource with ID DirectoryCopy"
            DependsOn = "[File]DirectoryCopy" # Depends on successful execution of the File resource.
        }
    }
}
```

Para saber mais sobre como usar **Credentials** no DSC, confira [Executar como usuário](../../../configurations/runAsUser.md) ou [Configurar credenciais de dados](../../../configurations/configDataCredentials.md).
