---
title: Funções
description: As funções do PowerShell permitem que você crie ferramentas que podem ser reutilizadas em scripts.
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: ca48f3020fa306f8a24328bd18648d5954c48a94
ms.sourcegitcommit: 0d958eac5bde5ccf5ee2c1bac4f009a63bf71368
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2020
ms.locfileid: "84438197"
---
# <a name="chapter-9---functions"></a>Capítulo 9 – Funções

Se você estiver escrevendo um ou mais scripts do PowerShell e acreditar que está sempre precisando modificá-los para diferentes cenários, há uma boa chance de que ele seja um bom candidato a ser transformado em uma função que possa ser reutilizada.

Sempre que possível, prefiro escrever funções porque elas são mais orientadas por ferramentas. Posso colocar as funções em um módulo de script, colocar esse módulo em `$env:PSModulePath` e chamar as funções sem precisar localizar fisicamente o local em que elas foram salvas. Usando o módulo PowerShellGet, é fácil compartilhar esses módulos em um repositório do NuGet. O PowerShellGet é fornecido no PowerShell versão 5.0 e superior. Ele está disponível como um download separado para o PowerShell versão 3.0 e superior.

Não complique demais. Mantenha a simplicidade e use a maneira mais direta de realizar uma tarefa. Evite aliases e parâmetros posicionais em qualquer código que você reutilize. Formate seu código para facilitar a leitura. Não embuta os valores em código. Use parâmetros e variáveis. Não escreva código desnecessário mesmo que isso não prejudique nada. Ele adiciona complexidade desnecessária. A atenção aos detalhes ajuda muito ao escrever qualquer código do PowerShell.

## <a name="naming"></a>Nomenclatura

Ao nomear suas funções no PowerShell, use um nome [Pascal case][] com um verbo aprovado e um substantivo singular. Também recomendo a prefixação do substantivo. Por exemplo: `<ApprovedVerb>-<Prefix><SingularNoun>`.

No PowerShell, há uma lista específica de verbos aprovados que podem ser obtidos executando `Get-Verb`.

```powershell
Get-Verb | Sort-Object -Property Verb
```

```Output
Verb        Group
----        -----
Add         Common
Approve     Lifecycle
Assert      Lifecycle
Backup      Data
Block       Security
Checkpoint  Data
Clear       Common
Close       Common
Compare     Data
Complete    Lifecycle
Compress    Data
Confirm     Lifecycle
Connect     Communications
Convert     Data
ConvertFrom Data
ConvertTo   Data
Copy        Common
Debug       Diagnostic
Deny        Lifecycle
Disable     Lifecycle
Disconnect  Communications
Dismount    Data
Edit        Data
Enable      Lifecycle
Enter       Common
Exit        Common
Expand      Data
Export      Data
Find        Common
Format      Common
Get         Common
Grant       Security
Group       Data
Hide        Common
Import      Data
Initialize  Data
Install     Lifecycle
Invoke      Lifecycle
Join        Common
Limit       Data
Lock        Common
Measure     Diagnostic
Merge       Data
Mount       Data
Move        Common
New         Common
Open        Common
Optimize    Common
Out         Data
Ping        Diagnostic
Pop         Common
Protect     Security
Publish     Data
Push        Common
Read        Communications
Receive     Communications
Redo        Common
Register    Lifecycle
Remove      Common
Rename      Common
Repair      Diagnostic
Request     Lifecycle
Reset       Common
Resize      Common
Resolve     Diagnostic
Restart     Lifecycle
Restore     Data
Resume      Lifecycle
Revoke      Security
Save        Data
Search      Common
Select      Common
Send        Communications
Set         Common
Show        Common
Skip        Common
Split       Common
Start       Lifecycle
Step        Common
Stop        Lifecycle
Submit      Lifecycle
Suspend     Lifecycle
Switch      Common
Sync        Data
Test        Diagnostic
Trace       Diagnostic
Unblock     Security
Undo        Common
Uninstall   Lifecycle
Unlock      Common
Unprotect   Security
Unpublish   Data
Unregister  Lifecycle
Update      Data
Use         Other
Wait        Lifecycle
Watch       Common
Write       Communications
```

No exemplo anterior, classifiquei os resultados pela coluna **Verb**. A coluna **Group** dá uma ideia de como esses verbos são usados. É importante escolher um verbo aprovado no PowerShell quando as funções são adicionadas a um módulo. O módulo vai gerar uma mensagem de aviso no tempo de carregamento se você escolher um verbo não aprovado. Essa mensagem de aviso faz com que suas funções pareçam não profissionais. Os verbos não aprovados também limitam a capacidade de descoberta de suas funções.

## <a name="a-simple-function"></a>Uma função simples

Uma função no PowerShell é declarada com a palavra-chave function seguida pelo nome da função e, em seguida, uma chave de abertura e fechamento. O código que a função executará está contido nessas chaves.

```powershell
function Get-Version {
    $PSVersionTable.PSVersion
}
```

A função mostrada é um exemplo simples que retorna a versão do PowerShell.

```powershell
Get-Version
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      14393  693
```

Há uma boa chance de conflito de nome com funções que têm um nome como `Get-Version` e comandos padrão no PowerShell ou comandos que outras pessoas possam escrever. É por isso que recomendo a prefixação da parte do substantivo de suas funções para ajudar a evitar conflitos de nomenclatura. No exemplo a seguir, usarei o prefixo "PS".

```powershell
function Get-PSVersion {
    $PSVersionTable.PSVersion
}
```

Além do nome, essa função é idêntica à anterior.

```powershell
Get-PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      14393  693
```

Mesmo ao prefixar o substantivo com algo como o PS, ainda há uma boa chance de ter um conflito de nome. Normalmente, prefixarei meus substantivos de função com minhas iniciais. Desenvolva um padrão e se atenha a ele.

```powershell
function Get-MrPSVersion {
    $PSVersionTable.PSVersion
}
```

Essa função não é diferente das duas anteriores, além de usar um nome mais sensato para tentar evitar conflitos de nomenclatura com outros comandos do PowerShell.

```powershell
Get-MrPSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      14393  693
```

Uma vez carregadas na memória, você poderá ver funções na PSDrive **Function**.

```powershell
Get-ChildItem -Path Function:\Get-*Version
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Function        Get-Version
Function        Get-PSVersion
Function        Get-MrPSVersion
```

Se desejar remover essas funções da sessão atual, você precisará removê-las da PSDrive **Function** ou fechar e reabrir o PowerShell.

```powershell
Get-ChildItem -Path Function:\Get-*Version | Remove-Item
```

Verifique se as funções foram realmente removidas.

```powershell
Get-ChildItem -Path Function:\Get-*Version
```

Se as funções tiverem sido carregadas como parte de um módulo, o módulo poderá ser descarregado para removê-las.

```powershell
Remove-Module -Name <ModuleName>
```

O cmdlet `Remove-Module` remove módulos da memória na sua sessão atual do PowerShell, ele não os remove do seu sistema ou do disco.

## <a name="parameters"></a>Parâmetros

Não atribua valores estaticamente. Use parâmetros e variáveis. Ao nomear parâmetros, use o mesmo nome que os cmdlets padrão para seus nomes de parâmetro sempre que possível.

```powershell
function Test-MrParameter {

    param (
        $ComputerName
    )

    Write-Output $ComputerName

}
```

Por que usei **ComputerName** e não **Computer**, **ServerName** ou **Host** para meu nome de parâmetro? Porque eu queria que minha função fosse padronizada como os cmdlets padrão.

Criarei uma função para consultar todos os comandos em um sistema e retornar quantos deles têm nomes de parâmetro específicos.

```powershell
function Get-MrParameterCount {
    param (
        [string[]]$ParameterName
    )

    foreach ($Parameter in $ParameterName) {
        $Results = Get-Command -ParameterName $Parameter -ErrorAction SilentlyContinue

        [pscustomobject]@{
            ParameterName = $Parameter
            NumberOfCmdlets = $Results.Count
        }
    }
}
```

Como você pode ver nos resultados mostrados abaixo, 39 comandos têm um parâmetro **ComputerName**. Não há cmdlets com parâmetros como **Computer**, **ServerName**, **Host** ou **Machine**.

```powershell
Get-MrParameterCount -ParameterName ComputerName, Computer, ServerName, Host, Machine
```

```Output
ParameterName NumberOfCmdlets
------------- ---------------
ComputerName               39
Computer                    0
ServerName                  0
Host                        0
Machine                     0
```

Também recomendo usar as mesmas letras maiúsculas e minúsculas para os nomes de parâmetro que os cmdlets padrão. Use `ComputerName`, não `computername`. Isso faz com que suas funções se pareçam com os cmdlets padrão. As pessoas que já estão familiarizadas com o PowerShell se sentirão em casa.

## <a name="advanced-functions"></a>Funções avançadas

Transformar uma função no PowerShell em uma função avançada é realmente simples. Uma das diferenças entre uma função e uma função avançada é que as funções avançadas têm um número de parâmetros comuns que são adicionados à função automaticamente. Esses parâmetros comuns incluem parâmetros como **Verbose** e **Debug**.

Começarei com a função `Test-MrParameter` que foi usada na seção anterior.

```powershell
function Test-MrParameter {

    param (
        $ComputerName
    )

    Write-Output $ComputerName

}
```

Observe que a função `Test-MrParameter` não tem nenhum parâmetro comum. Há algumas maneiras diferentes de ver os parâmetros comuns. Uma delas é exibir a sintaxe usando `Get-Command`.

```powershell
Get-Command -Name Test-MrParameter -Syntax
```

```Output
Test-MrParameter [[-ComputerName] <Object>]
```

Outra é fazer uma busca detalhada nos parâmetros com `Get-Command`.

```powershell
(Get-Command -Name Test-MrParameter).Parameters.Keys
```

```Output
ComputerName
```

Adicione `CmdletBinding` para transformar a função em uma função avançada.

```powershell
function Test-MrCmdletBinding {

    [CmdletBinding()] #<<-- This turns a regular function into an advanced function
    param (
        $ComputerName
    )

    Write-Output $ComputerName

}
```

Adicionar `CmdletBinding` adiciona os parâmetros comuns automaticamente. `CmdletBinding` requer um bloco de `param`, mas o bloco de `param` pode estar vazio.

```powershell
Get-Command -Name Test-MrCmdletBinding -Syntax
```

```Output
Test-MrCmdletBinding [[-ComputerName] <Object>] [<CommonParameters>]
```

Analisar detalhadamente os parâmetros com `Get-Command` mostra os nomes de parâmetro reais, incluindo os comuns.

```powershell
(Get-Command -Name Test-MrCmdletBinding).Parameters.Keys
```

```Output
ComputerName
Verbose
Debug
ErrorAction
WarningAction
InformationAction
ErrorVariable
WarningVariable
InformationVariable
OutVariable
OutBuffer
PipelineVariable
```

## <a name="supportsshouldprocess"></a>SupportsShouldProcess

`SupportsShouldProcess` adiciona os parâmetros **WhatIf** e **Confirm**. Eles são necessários apenas para comandos que fazem alterações.

```powershell
function Test-MrSupportsShouldProcess {

    [CmdletBinding(SupportsShouldProcess)]
    param (
        $ComputerName
    )

    Write-Output $ComputerName

}
```

Observe que agora há os parâmetros **WhatIf** e **Confirm**.

```powershell
Get-Command -Name Test-MrSupportsShouldProcess -Syntax
```

```Output
Test-MrSupportsShouldProcess [[-ComputerName] <Object>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

Mais uma vez, você também pode usar `Get-Command` para retornar uma lista dos nomes de parâmetro reais, incluindo os comuns, juntamente com WhatIf e Confirm.

```powershell
(Get-Command -Name Test-MrSupportsShouldProcess).Parameters.Keys
```

```Output
ComputerName
Verbose
Debug
ErrorAction
WarningAction
InformationAction
ErrorVariable
WarningVariable
InformationVariable
OutVariable
OutBuffer
PipelineVariable
WhatIf
Confirm
```

## <a name="parameter-validation"></a>Validação de parâmetro

Valide a entrada no início. Por que o código pode continuar em um caminho quando não é possível executá-lo sem uma entrada válida?

Sempre digite as variáveis que estão sendo usadas para seus parâmetros (especifique um tipo de dados).

```powershell
function Test-MrParameterValidation {

    [CmdletBinding()]
    param (
        [string]$ComputerName
    )

    Write-Output $ComputerName

}
```

No exemplo anterior, especifiquei **String** como o tipo de dados do parâmetro **ComputerName**. Isso faz com que ele permita que apenas um único nome do computador seja especificado. Se mais de um nome do computador for especificado por meio de uma lista separada por vírgulas, um erro será gerado.

```powershell
Test-MrParameterValidation -ComputerName Server01, Server02
```

```Output
Test-MrParameterValidation : Cannot process argument transformation on parameter
'ComputerName'. Cannot convert value to type System.String.
At line:1 char:42
+ Test-MrParameterValidation -ComputerName Server01, Server02
+
    + CategoryInfo          : InvalidData: (:) [Test-MrParameterValidation], ParameterBindingArg
     umentTransformationException
    + FullyQualifiedErrorId : ParameterArgumentTransformationError,Test-MrParameterValidation
```

O problema com a definição atual é que ela é válida para omitir o valor do parâmetro **ComputerName**, mas um valor é necessário para que a função seja concluída com êxito. É aí que o atributo de parâmetro `Mandatory` é útil.

```powershell
function Test-MrParameterValidation {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory)]
        [string]$ComputerName
    )

    Write-Output $ComputerName

}
```

A sintaxe usada no exemplo anterior é compatível com o PowerShell versão 3.0 e superiores.
`[Parameter(Mandatory=$true)]` pode ser especificado em vez de tornar a função compatível com o PowerShell versão 2.0 e superiores. Agora que o **ComputerName** é necessário, se um não for especificado, a função o solicitará.

```powershell
Test-MrParameterValidation
```

```Output
cmdlet Test-MrParameterValidation at command pipeline position 1
Supply values for the following parameters:
ComputerName:
```

Se você quiser permitir mais de um valor para o parâmetro **ComputerName**, use o tipo de dados **String**, mas adicione colchetes abertos e fechados ao tipo de dados para permitir uma matriz de cadeias de caracteres.

```powershell
function Test-MrParameterValidation {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory)]
        [string[]]$ComputerName
    )

    Write-Output $ComputerName

}
```

Talvez você queira especificar um valor padrão para o parâmetro **ComputerName** se um não tiver especificado.
O problema é que os valores padrão não podem ser usados com parâmetros obrigatórios. Em vez disso, você precisará usar o atributo de validação de parâmetro `ValidateNotNullOrEmpty` com um valor padrão.

```powershell
function Test-MrParameterValidation {

    [CmdletBinding()]
    param (
        [ValidateNotNullOrEmpty()]
        [string[]]$ComputerName = $env:COMPUTERNAME
    )

    Write-Output $ComputerName

}
```

Mesmo ao definir um valor padrão, tente não usar valores estáticos. No exemplo anterior, `$env:COMPUTERNAME` é usado como o valor padrão, que será automaticamente convertido no nome do computador local se um valor não for fornecido.

## <a name="verbose-output"></a>Saída detalhada

Embora comentários embutidos sejam úteis, especialmente se você estiver escrevendo um código complexo, eles nunca serão vistos pelos usuários, a menos que eles examinem o próprio código.

A função mostrada no exemplo a seguir tem um comentário embutido no loop de `foreach`. Embora esse comentário específico não seja tão difícil de localizar, imagine se a função incluísse centenas de linhas de código.

```powershell
function Test-MrVerboseOutput {

    [CmdletBinding()]
    param (
        [ValidateNotNullOrEmpty()]
        [string[]]$ComputerName = $env:COMPUTERNAME
    )

    foreach ($Computer in $ComputerName) {
        #Attempting to perform some action on $Computer <<-- Don't use
        #inline comments like this, use write verbose instead.
        Write-Output $Computer
    }

}
```

Uma opção melhor é usar `Write-Verbose` em vez de comentários embutidos.

```powershell
function Test-MrVerboseOutput {

    [CmdletBinding()]
    param (
        [ValidateNotNullOrEmpty()]
        [string[]]$ComputerName = $env:COMPUTERNAME
    )

    foreach ($Computer in $ComputerName) {
        Write-Verbose -Message "Attempting to perform some action on $Computer"
        Write-Output $Computer
    }

}
```

Quando a função é chamada sem o parâmetro **Verbose**, a saída detalhada não é exibida.

```powershell
Test-MrVerboseOutput -ComputerName Server01, Server02
```

Quando for chamado com o parâmetro **Verbose**, a saída detalhada será exibida.

```powershell
Test-MrVerboseOutput -ComputerName Server01, Server02 -Verbose
```

## <a name="pipeline-input"></a>Entrada do pipeline

Quando você quiser que sua função aceite a entrada do pipeline, é necessária alguma codificação adicional. Como mencionado anteriormente neste livro, os comandos podem aceitar a entrada do pipeline **por valor** (por tipo) ou **por nome da propriedade**. Você pode escrever suas funções exatamente como os comandos nativos para que aceitem um ou ambos os tipos de entrada.

Para aceitar a entrada de pipeline **por valor**, especifique o atributo de parâmetro `ValueFromPipeline` para esse parâmetro específico. Lembre-se de que você só pode aceitar a entrada de pipeline **por valor** de um de cada tipo de dados. Por exemplo, se você tiver dois parâmetros que aceitam a entrada de cadeia de caracteres, somente um deles poderá aceitar a entrada de pipeline **por valor** porque, se você o tiver especificado para ambos os parâmetros de cadeia de caracteres, a entrada do pipeline não saberá a qual deles se associar. Essa é outra razão pela qual eu chamo esse tipo de entrada de pipeline _por tipo_, em vez de **por valor**.

A entrada do pipeline vem em um item de cada vez, de maneira semelhante a como os itens são manipulados em um loop de `foreach`.
No mínimo, um bloco `process` será necessário para processar cada um desses itens se você estiver aceitando uma matriz como entrada. Se você estiver aceitando apenas um único valor como entrada, um bloco de `process` não será necessário, mas eu ainda recomendo especificá-lo para fins de consistência.

```powershell
function Test-MrPipelineInput {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory,
                   ValueFromPipeline)]
        [string[]]$ComputerName
    )

    PROCESS {
        Write-Output $ComputerName
    }

}
```

Aceitar a entrada do pipeline **pelo nome da propriedade** é semelhante, exceto pelo fato de ser especificado com o atributo de parâmetro `ValueFromPipelineByPropertyName` e pode ser especificado para qualquer número de parâmetros, independentemente do tipo de dados. A chave é que a saída do comando que está sendo canalizado deve ter um nome de propriedade que corresponda ao nome do parâmetro ou a um alias de parâmetro de sua função.

```powershell
function Test-MrPipelineInput {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory,
                   ValueFromPipelineByPropertyName)]
        [string[]]$ComputerName
    )

    PROCESS {
            Write-Output $ComputerName
    }

}
```

Os blocos de `BEGIN` e `END` são opcionais. `BEGIN` seria especificado antes do bloco de `PROCESS` e é usado para executar qualquer trabalho inicial antes dos itens que estão sendo recebidos do pipeline. É importante entender isso. Os valores que são canalizados para dentro não estão acessíveis no bloco de `BEGIN`. O bloco de `END` seria especificado após o bloco de `PROCESS` e é usado para limpeza depois que todos os itens que foram canalizados para dentro foram processados.

## <a name="error-handling"></a>Tratamento de erros

A função mostrada no exemplo a seguir gera uma exceção sem tratamento quando um computador não pode ser contatado.

```powershell
function Test-MrErrorHandling {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory,
                   ValueFromPipeline,
                   ValueFromPipelineByPropertyName)]
        [string[]]$ComputerName
    )

    PROCESS {
        foreach ($Computer in $ComputerName) {
            Test-WSMan -ComputerName $Computer
        }
    }

}
```

Há algumas maneiras diferentes de lidar com erros no PowerShell. `Try/Catch` é a maneira mais moderna de lidar com erros.

```powershell
function Test-MrErrorHandling {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory,
                   ValueFromPipeline,
                   ValueFromPipelineByPropertyName)]
        [string[]]$ComputerName
    )

    PROCESS {
        foreach ($Computer in $ComputerName) {
            try {
                Test-WSMan -ComputerName $Computer
            }
            catch {
                Write-Warning -Message "Unable to connect to Computer: $Computer"
            }
        }
    }

}
```

Embora a função mostrada no exemplo anterior use o tratamento de erro, ela também gera uma exceção sem tratamento, pois o comando não gera um erro de encerramento. Também é importante entender isso. Somente erros de encerramento são capturados. Especifique o parâmetro **ErrorAction** com **Stop** como o valor para transformar um erro de não finalização em um encerramento.

```powershell
function Test-MrErrorHandling {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory,
                   ValueFromPipeline,
                   ValueFromPipelineByPropertyName)]
        [string[]]$ComputerName
    )

    PROCESS {
        foreach ($Computer in $ComputerName) {
            try {
                Test-WSMan -ComputerName $Computer -ErrorAction Stop
            }
            catch {
                Write-Warning -Message "Unable to connect to Computer: $Computer"
            }
        }
    }

}
```

Não modifique a variável `$ErrorActionPreference` global, a menos que seja absolutamente necessário. Se você estiver usando algo como o .NET diretamente de dentro de sua função do PowerShell, não poderá especificar a **ErrorAction** no próprio comando. Nesse cenário, talvez seja preciso alterar a variável de `$ErrorActionPreference` global, mas se você alterá-la, faça isso imediatamente depois de tentar o comando.

## <a name="comment-based-help"></a>Ajuda baseada em comentários

É considerada uma melhor prática adicionar ajuda com base em comentários às suas funções para que as pessoas com as quais você está compartilhando saibam saber como usá-las.

```powershell
function Get-MrAutoStoppedService {

<#
.SYNOPSIS
    Returns a list of services that are set to start automatically, are not
    currently running, excluding the services that are set to delayed start.

.DESCRIPTION
    Get-MrAutoStoppedService is a function that returns a list of services from
    the specified remote computer(s) that are set to start automatically, are not
    currently running, and it excludes the services that are set to start automatically
    with a delayed startup.

.PARAMETER ComputerName
    The remote computer(s) to check the status of the services on.

.PARAMETER Credential
    Specifies a user account that has permission to perform this action. The default
    is the current user.

.EXAMPLE
     Get-MrAutoStoppedService -ComputerName 'Server1', 'Server2'

.EXAMPLE
     'Server1', 'Server2' | Get-MrAutoStoppedService

.EXAMPLE
     Get-MrAutoStoppedService -ComputerName 'Server1' -Credential (Get-Credential)

.INPUTS
    String

.OUTPUTS
    PSCustomObject

.NOTES
    Author:  Mike F Robbins
    Website: http://mikefrobbins.com
    Twitter: @mikefrobbins
#>

    [CmdletBinding()]
    param (

    )

    #Function Body

}
```

Quando você adiciona ajuda com base em comentários às suas funções, é possível recuperar a ajuda para elas, assim como os comandos internos padrão.

Toda a sintaxe para escrever uma função no PowerShell pode parecer difícil principalmente para alguém que está recém começando. Com frequência, se eu não me lembrar da sintaxe de algo, abrirei uma segunda cópia do ISE em um monitor separado e exibirei o snippet "cmdlet (advanced function) - Complete" ao digitar o código para a minha função. Os snippets de código podem ser acessados no ISE do PowerShell usando a combinação de teclas <kbd>Ctrl</kbd>+<kbd>J</kbd>.

## <a name="summary"></a>Resumo

Neste capítulo, você aprendeu as noções básicas de como escrever funções no PowerShell para incluir como transformar uma função em uma função avançada e alguns dos elementos mais importantes que você deve considerar ao escrever funções do PowerShell, como validação de parâmetro, saída detalhada, entrada de pipeline, tratamento de erro e ajuda baseada em comentários.

## <a name="review"></a>Revisão

1. Como obter uma lista de verbos aprovados no PowerShell?
1. Como transformar uma função do PowerShell em uma função avançada?
1. Quando os parâmetros **WhatIf** e **Confirm** devem ser adicionados às funções do PowerShell?
1. Como você transforma um erro não de encerramento em um de encerramento?
1. Por que você deve adicionar ajuda baseada em comentários às suas funções?

## <a name="recommended-reading"></a>Leitura recomendada

- [about_Functions][]
- [about_Functions_Advanced_Parameters][]
- [about_CommonParameters][]
- [about_Functions_CmdletBindingAttribute][]
- [about_Functions_Advanced][]
- [about_Try_Catch_Finally][]
- [about_Comment_Based_Help][]
- [Vídeo: Toolmaking do PowerShell com funções avançadas e módulos de script][]

<!-- link references -->
[about_Functions]: /powershell/module/microsoft.powershell.core/about/about_functions
[about_Functions_Advanced_Parameters]: /powershell/module/microsoft.powershell.core/about/about_functions_advanced_parameters
[about_CommonParameters]: /powershell/module/microsoft.powershell.core/about/about_commonparameters
[about_Functions_CmdletBindingAttribute]: /powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute
[about_Functions_Advanced]: /powershell/module/microsoft.powershell.core/about/about_functions_advanced
[about_Try_Catch_Finally]: /powershell/module/microsoft.powershell.core/about/about_try_catch_finally
[about_Comment_Based_Help]: /powershell/module/microsoft.powershell.core/about/about_comment_based_help
[Vídeo: Toolmaking do PowerShell com funções avançadas e módulos de script]: https://mikefrobbins.com/2016/05/26/video-powershell-toolmaking-with-advanced-functions-and-script-modules/) [Pascal case]: /dotnet/standard/design-guidelines/capitalization-conventionss
