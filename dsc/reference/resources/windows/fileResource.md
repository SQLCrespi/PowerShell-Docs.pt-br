---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Recursos File de DSC
ms.openlocfilehash: b5bc2c305b8cfccbd044274811df631264a24279
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62077323"
---
# <a name="dsc-file-resource"></a>Recursos File de DSC

> Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.0

O recurso File na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para gerenciar arquivos e pastas no nó de destino. O **DestinationPath** e o **SourcePath** devem ser acessíveis pelo nó de destino.

## <a name="syntax"></a>Sintaxe

```
File [string] #ResourceName
{
    DestinationPath = [string]
    [ Attributes = [string[]] { Archive | Hidden | ReadOnly | System }]
    [ Checksum = [string] { CreatedDate | ModifiedDate | SHA-1 | SHA-256 | SHA-512 } ]
    [ Contents = [string] ]
    [ Credential = [PSCredential] ]
    [ Ensure = [string] { Absent | Present } ]
    [ Force = [bool] ]
    [ Recurse = [bool] ]
    [ DependsOn = [string[]] ]
    [ SourcePath = [string] ]
    [ Type = [string] { Directory | File } ]
    [ MatchSource = [bool] ]
}
```

## <a name="properties"></a>Propriedades

|Propriedade       |Descrição                                                                   |Necessária|Padrão|
|---------------|------------------------------------------------------------------------------|--------|-------|
|DestinationPath|O local, no nó de destino, que você quer que seja `Present` ou `Absent`.|Sim|Não|
|Atributos     |O estado desejado dos atributos para o arquivo ou diretório de destino. Os valores válidos são **Archive**, **Hidden**, **ReadOnly** e **System**.|Não|Não|
|Soma de verificação      |O tipo de soma de verificação a usar para determinar se dois arquivos são iguais. Os valores válidos incluem: SHA-1, SHA-256, SHA-512, createdDate, modifiedDate.|Não|Apenas os nomes de arquivo ou de diretório são comparados.|
|Conteúdo       |Válido apenas quando usado com o tipo `File`. Indica se o conteúdo a verificar está `Present` ou `Absent` no arquivo de destino. |Não|Não|
|Credential     |As credenciais necessárias para acessar recursos, como arquivos de origem.|Não|A conta do computador do nó de destino. (*veja a observação*)|
|Ensure         |O estado desejado do diretório ou arquivo de destino. |Não|**Presente**|
|Force          |Substitui as operações de acesso que resultariam em erro (como substituir um arquivo ou excluir um diretório que não esteja vazio).|Não|`$false`|
|Recurse        |Válido apenas quando usado com o tipo `Directory`. Executa recursivamente a operação de estado em todos os subdiretórios.|Não|`$false`|
|DependsOn      |Define uma dependência no(s) recurso(s) especificado(s). Este recurso só será executado após a execução bem-sucedida de todos os recursos dependentes. Você pode especificar os recursos dependentes usando a sintaxe `"[ResourceType]ResourceName"`. Consulte [about_DependsOn](../../../configurations/resource-depends-on.md)|Não|Não|
|SourcePath     |O caminho do qual o recurso de arquivo ou pasta deve ser copiado.|Não|Não|
|Tipo           |O tipo de recurso que está sendo configurado. Os valores válidos são `Directory` e `File`.|Não|`File`|
|MatchSource    |Determina se o recurso deve monitorar novos arquivos adicionados ao diretório de origem após a cópia inicial. Um valor `$true` indica que, após a cópia inicial, os novos arquivos de origem devem ser copiados para o destino. Se for definido como `$False`, o recurso armazena em cache o conteúdo do diretório de origem e ignora todos os arquivos adicionados após a cópia inicial.|Não|`$false`|

> [!WARNING]
> Se você não especificar um valor para `Credential` ou `PSRunAsCredential` (PS V.5), o recurso usará a conta de computador do nó de destino para acessar o `SourcePath`.  Quando o `SourcePath` é um compartilhamento UNC, isso pode resultar em um erro "Acesso negado". Verifique se suas permissões estão definidas adequadamente ou use as propriedades `Credential` ou `PSRunAsCredential` para especificar a conta que deve ser usada.

## <a name="present-vs-absent"></a>Present versus Absent

Cada recurso DSC executa operações diferentes com base no valor especificado para a propriedade `Ensure`. Os valores especificados para as propriedades acima determinam a operação de estado executada.

### <a name="existence"></a>Existência

Ao especificar apenas um `DestinationPath`, o recurso garante que o caminho existe (`Present`) ou não existe (`Absent`).

### <a name="copy-operations"></a>Operações de cópia

Quando você especifica um `SourcePath` e um `DestinationPath` com um valor `Type` do **Diretório**, o recurso copia o diretório de origem para o caminho de destino. As propriedades `Recurse`, `Force` e `MatchSource` alteram o tipo de operação de cópia executada, embora `Credential` determine qual conta usar para acessar o diretório de origem.

### <a name="limitations"></a>Limitações

Se você tiver especificado um valor `ReadOnly` para a propriedade `Attributes` com um `DestinationPath`, `Ensure = "Present"` criará o caminho especificado, enquanto `Contents` definirá o conteúdo do arquivo.  Uma operação de estado `Absent` ignoraria completamente a propriedade `Attributes` e removeria qualquer arquivo no caminho especificado.

## <a name="example"></a>Exemplo

O exemplo a seguir copia um diretório e seus subdiretórios de um servidor de pull para um nó de destino usando o recurso de arquivo. Se a operação for bem-sucedida, o recurso de Log gravará uma mensagem de confirmação no log de eventos.

O diretório de origem é um caminho UNC (`\\PullServer\DemoSource`) compartilhado do servidor de pull. A propriedade `Recurse` garante que todos os subdiretórios também sejam copiados.

> [!IMPORTANT]
> O LCM no nó de destino é executado no contexto da conta do sistema local por padrão. Para conceder acesso ao **SourcePath**, dê à conta do computador do nó de destino as permissões apropriadas. **Credential** e **PSDSCRunAsCredential** (v5) alteram o contexto que o LCM usa para acessar o **SourcePath**. Você ainda precisa conceder acesso à conta a ser usada para acessar o **SourcePath**.

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
