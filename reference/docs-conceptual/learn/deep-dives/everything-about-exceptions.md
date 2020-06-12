---
title: Tudo o que você queria saber sobre exceções
description: O tratamento de erro é apenas uma parte da vida quando se trata de escrever código.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 3ecb1669fa8d58bc742d4e8e77051b3ace4452a0
ms.sourcegitcommit: 4a40e3ea3601c02366be3495a5dcc7f4cac9f1ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2020
ms.locfileid: "84337175"
---
# <a name="everything-you-wanted-to-know-about-exceptions"></a>Tudo o que você queria saber sobre exceções

O tratamento de erro é apenas uma parte da vida quando se trata de escrever código. Geralmente, podemos verificar e validar condições para um comportamento esperado. Quando o erro é inesperado, recorreremos à manipulação de exceção. Você pode facilmente manipular exceções geradas pelo código de outras pessoas ou pode gerar as suas próprias exceções para que outras pessoas as manipulem.

> [!NOTE]
> A [versão original][] deste artigo apareceu no blog escrito por [@KevinMarquette][]. A equipe do PowerShell agradece ao Kevin por compartilhar esse conteúdo conosco. Confira o blog dele em [PowerShellExplained.com][].

## <a name="basic-terminology"></a>Terminologia básica

Precisamos abordar alguns termos básicos antes de continuarmos.

### <a name="exception"></a>Exceção

Uma Exceção é como um evento que é criado quando o tratamento de erro normal não pode lidar com o problema.
Tentar dividir um número por zero ou ficar sem memória são exemplos de algo que cria uma exceção. Às vezes, o autor do código que você está usando cria exceções para determinados problemas quando eles acontecem.

### <a name="throw-and-catch"></a>Gerar e capturar

Quando ocorre uma exceção, dizemos que uma exceção é gerada. Para manipular uma exceção gerada, você precisa capturá-la. Se uma exceção for gerada e não for capturada por algo, o script parará de ser executado.

### <a name="the-call-stack"></a>A pilha de chamadas

A pilha de chamadas é a lista de funções que chamaram umas às outras. Quando uma função é chamada, ela é adicionada à pilha ou ao começo da lista. Quando a função sai ou retorna, ela é removida da pilha.

Quando uma exceção é gerada, essa pilha de chamadas é verificada para que um manipulador de exceção a capture.

### <a name="terminating-and-non-terminating-errors"></a>Erros de encerramento e de não encerramento

Uma exceção é geralmente um erro de encerramento. Uma exceção gerada é capturada ou termina a execução atual. Por padrão, um erro de não encerramento é gerado pelo `Write-Error` e ele adiciona um erro ao fluxo de saída sem gerar uma exceção.

Ressaltei isso porque `Write-Error` e outros erros de não encerramento não disparam o `catch`.

### <a name="swallowing-an-exception"></a>Assimilando uma exceção

Isso ocorre quando você captura um erro apenas para suprimi-lo. Faça isso com cautela porque pode dificultar bastante a solução de problemas.

## <a name="basic-command-syntax"></a>Sintaxe de comando básica

A seguir está uma rápida visão geral da sintaxe básica de manipulação de exceção usada no PowerShell.

### <a name="throw"></a>Throw

Para criar o nosso próprio evento de exceção, geramos uma exceção com a palavra-chave `throw`.

```powershell
function Start-Something
{
    throw "Bad thing happened"
}
```

Isso cria uma exceção de runtime que é um erro de encerramento. Ele é manipulado por um `catch` em uma função de chamada ou sai do script com uma mensagem como esta.

```powershell
PS> Start-Something

Bad thing happened
At line:1 char:1
+ throw "Bad thing happened"
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : OperationStopped: (Bad thing happened:String) [], RuntimeException
    + FullyQualifiedErrorId : Bad thing happened
```

#### <a name="write-error--erroraction-stop"></a>Write-Error -ErrorAction Stop

Mencionei que o `Write-Error` não gera um erro de encerramento por padrão. Se você especificar `-ErrorAction Stop`, `Write-Error` gerará um erro de encerramento que pode ser manipulado com um `catch`.

```powershell
Write-Error -Message "Houston, we have a problem." -ErrorAction Stop
```

Agradeço a Lee Daily por lembrar sobre o uso de `-ErrorAction Stop` dessa maneira.

#### <a name="cmdlet--erroraction-stop"></a>Cmdlet -ErrorAction Stop

Se você especificar `-ErrorAction Stop` em qualquer função ou cmdlet avançado, ele transformará todas as instruções `Write-Error` em erros de encerramento que interromperão a execução ou que poderão ser manipulados por um `catch`.

```powershell
Start-Something -ErrorAction Stop
```

### <a name="trycatch"></a>Try/Catch

A maneira como a manipulação de exceção funciona no PowerShell (e em muitas outras linguagens) é que você primeiro realiza `try` em uma seção de código e, se ele gerar um erro, você poderá realizar `catch` nela. Aqui está um exemplo rápido.

```powershell
try
{
    Start-Something
}
catch
{
    Write-Output "Something threw an exception"
}

try
{
    Start-Something -ErrorAction Stop
}
catch
{
    Write-Output "Something threw an exception or used Write-Error"
}
```

O script `catch` só será executado se houver um erro de encerramento. Se o `try` for executado corretamente, ele ignorará o `catch`.

### <a name="tryfinally"></a>Try/Finally

Às vezes, você não precisa tratar um erro, mas ainda precisa que algum código seja executado se uma exceção ocorrer ou não. Um script `finally` faz exatamente isso.

Veja este exemplo:

```powershell
$command = [System.Data.SqlClient.SqlCommand]::New(queryString, connection)
$command.Connection.Open()
$command.ExecuteNonQuery()
$command.Connection.Close()
```

Sempre que você abrir ou se conectar a um recurso, deverá fechá-lo. Se o `ExecuteNonQuery()` gera uma exceção, a conexão não é fechada. A seguir está o mesmo código dentro de um bloco `try/finally`.

```powershell
$command = [System.Data.SqlClient.SqlCommand]::New(queryString, connection)
try
{
    $command.Connection.Open()
    $command.ExecuteNonQuery()
}
finally
{
    $command.Connection.Close()
}
```

Nesse exemplo, a conexão será encerrada se houver um erro. Ela também será encerrada se não houver erro. O script `finally` é executado todas as vezes.

Como você não está capturando a exceção, ela ainda será propagada na pilha de chamadas.

### <a name="trycatchfinally"></a>Try/Catch/Finally

É perfeitamente válido usar `catch` e `finally` juntos. Na maioria das vezes, você usará um ou outro, mas poderá encontrar cenários em que usa ambos.

## <a name="psitem"></a>$PSItem

Agora que explicamos as noções básicas, podemos nos aprofundar um pouco mais.

Dentro do bloco `catch`, há uma variável automática (`$PSItem` ou `$_`) do tipo `ErrorRecord` que contém os detalhes sobre a exceção. A seguir está uma visão geral rápida de algumas das principais propriedades.

Nesses exemplos, usei um caminho inválido em `ReadAllText` para gerar a exceção.

```powershell
[System.IO.File]::ReadAllText( '\\test\no\filefound.log')
```

### <a name="psitemtostring"></a>PSItem.ToString()

Isso lhe fornece a mensagem mais limpa a ser usada no registro em log e na saída geral. `ToString()` será chamado automaticamente se `$PSItem` for colocado em uma cadeia de caracteres.

```powershell
catch
{
    Write-Output "Ran into an issue: $($PSItem.ToString())"
}

catch
{
    Write-Output "Ran into an issue: $PSItem"
}
```

### <a name="psiteminvocationinfo"></a>$PSItem.InvocationInfo

Essa propriedade contém informações adicionais coletadas pelo PowerShell sobre a função ou o script no qual a exceção foi gerada. A seguir está o `InvocationInfo` da exceção de exemplo que criei.

```powershell
PS> $PSItem.InvocationInfo | Format-List *

MyCommand             : Get-Resource
BoundParameters       : {}
UnboundArguments      : {}
ScriptLineNumber      : 5
OffsetInLine          : 5
ScriptName            : C:\blog\throwerror.ps1
Line                  :     Get-Resource
PositionMessage       : At C:\blog\throwerror.ps1:5 char:5
                        +     Get-Resource
                        +     ~~~~~~~~~~~~
PSScriptRoot          : C:\blog
PSCommandPath         : C:\blog\throwerror.ps1
InvocationName        : Get-Resource
```

Os detalhes importantes aqui mostram o `ScriptName`, o `Line` de código e o `ScriptLineNumber` em que a invocação foi iniciada.

### <a name="psitemscriptstacktrace"></a>$PSItem.ScriptStackTrace

Essa propriedade mostra a ordem das chamadas de função que levaram você ao código no qual a exceção foi gerada.

```powershell
PS> $PSItem.ScriptStackTrace
at Get-Resource, C:\blog\throwerror.ps1: line 13
at Start-Something, C:\blog\throwerror.ps1: line 5
at <ScriptBlock>, C:\blog\throwerror.ps1: line 18
```

Estou fazendo chamadas somente para funções no mesmo script, mas isso acompanharia as chamadas se vários scripts estivessem envolvidos.

### <a name="psitemexception"></a>$PSItem.Exception

Essa é a exceção real que foi gerada.

#### <a name="psitemexceptionmessage"></a>$PSItem.Exception.Message

Essa é a mensagem geral que descreve a exceção e é um bom ponto de partida ao solucionar problemas. A maioria das exceções tem uma mensagem padrão, mas também pode ser personalizada quando a exceção é gerada.

```powershell
PS> $PSItem.Exception.Message

Exception calling "ReadAllText" with "1" argument(s): "The network path was not found."
```

Essa também será a mensagem retornada ao chamar `$PSItem.ToString()`, se não houver uma definida em `ErrorRecord`.

#### <a name="psitemexceptioninnerexception"></a>$PSItem.Exception.InnerException

Exceções podem conter exceções internas. Geralmente, esse é o caso quando o código que você está chamando captura uma exceção e gera uma exceção diferente. A exceção original é colocada dentro da nova exceção.

```powershell
PS> $PSItem.Exception.InnerExceptionMessage
The network path was not found.
```

Vou revisitar isso mais tarde quando falar sobre gerar novamente exceções.

#### <a name="psitemexceptionstacktrace"></a>$PSItem.Exception.StackTrace

Este é o `StackTrace` para a exceção. Mostrei um `ScriptStackTrace` acima, mas esse é para as chamadas para o código gerenciado.

```Output
at System.IO.FileStream.Init(String path, FileMode mode, FileAccess access, Int32 rights, Boolean
 useRights, FileShare share, Int32 bufferSize, FileOptions options, SECURITY_ATTRIBUTES secAttrs,
 String msgPath, Boolean bFromProxy, Boolean useLongPath, Boolean checkHost)
at System.IO.FileStream..ctor(String path, FileMode mode, FileAccess access, FileShare share, Int32
 bufferSize, FileOptions options, String msgPath, Boolean bFromProxy, Boolean useLongPath, Boolean
 checkHost)
at System.IO.StreamReader..ctor(String path, Encoding encoding, Boolean detectEncodingFromByteOrderMarks,
 Int32 bufferSize, Boolean checkHost)
at System.IO.File.InternalReadAllText(String path, Encoding encoding, Boolean checkHost)
at CallSite.Target(Closure , CallSite , Type , String )
```

Você só obterá esse rastreamento de pilha quando o evento for gerado pelo código gerenciado. Estou chamando uma função do .NET Framework diretamente para que apenas ela seja exibida neste exemplo. Geralmente, quando você olha para um rastreamento de pilha, está procurando onde o seu código é interrompido e onde as chamadas do sistema começam.

## <a name="working-with-exceptions"></a>Trabalhando com exceções

Exceções são mais do que apenas a sintaxe básica e as propriedades da exceção.

### <a name="catching-typed-exceptions"></a>Capturando exceções tipadas

Você pode ser seletivo com as exceções que você captura. As exceções têm um tipo e você pode especificar o tipo de exceção que deseja capturar.

```powershell
try
{
    Start-Something -Path $path
}
catch [System.IO.FileNotFoundException]
{
    Write-Output "Could not find $path"
}
catch [System.IO.IOException]
{
        Write-Output "IO error with the file: $path"
}
```

O tipo de exceção é verificado para cada bloco `catch` até encontrar um que corresponda à sua exceção.
É importante perceber que as exceções podem ser herdadas de outras exceções. No exemplo acima, `FileNotFoundException` herda de `IOException`. Portanto, se o `IOException` foi primeiro, ele seria chamado em vez disso. Somente um bloco catch será invocado mesmo se houver várias correspondências.

Se tivéssemos um `System.IO.PathTooLongException`, o `IOException` seria correspondente, mas se tivéssemos um `InsufficientMemoryException`, nada o capturaria e ele propagaria a pilha.

### <a name="catch-multiple-types-at-once"></a>Capturar vários tipos de uma vez

É possível capturar vários tipos de exceção com a mesma instrução `catch`.

```powershell
try
{
    Start-Something -Path $path -ErrorAction Stop
}
catch [System.IO.DirectoryNotFoundException],[System.IO.FileNotFoundException]
{
    Write-Output "The path or file was not found: [$path]"
}
catch [System.IO.IOException]
{
    Write-Output "IO error with the file: [$path]"
}
```

Agradecemos a `/u/Sheppard_Ra` por sugerir essa adição.

### <a name="throwing-typed-exceptions"></a>Gerando exceções tipadas

Você pode gerar exceções tipadas no PowerShell. Em vez de chamar `throw` com uma cadeia de caracteres:

```powershell
throw "Could not find: $path"
```

Use um acelerador de exceção como este:

```powershell
throw [System.IO.FileNotFoundException] "Could not find: $path"
```

Mas você precisa especificar uma mensagem ao fazer isso dessa maneira.

Você também pode criar uma nova instância de uma exceção a ser gerada. A mensagem é opcional quando você faz isso porque o sistema tem mensagens padrão para todas as exceções internas.

```powershell
throw [System.IO.FileNotFoundException]::new()
throw [System.IO.FileNotFoundException]::new("Could not find path: $path")
```

Se você não estiver usando o PowerShell 5.0 ou superior, precisará usar a abordagem de `New-Object` mais antiga.

```powershell
throw (New-Object -TypeName System.IO.FileNotFoundException )
throw (New-Object -TypeName System.IO.FileNotFoundException -ArgumentList "Could not find path: $path")
```

Usando uma exceção tipada, você (ou outros) podem capturar a exceção pelo tipo, conforme mencionado na seção anterior.

#### <a name="write-error--exception"></a>Write-Error -Exception

Podemos adicionar essas exceções tipadas ao `Write-Error` e ainda podemos realizar `catch` nos erros por tipo de exceção. Use `Write-Error` como nestes exemplos:

```powershell
# with normal message
Write-Error -Message "Could not find path: $path" -Exception ([System.IO.FileNotFoundException]::new()) -ErrorAction Stop

# With message inside new exception
Write-Error -Exception ([System.IO.FileNotFoundException]::new("Could not find path: $path")) -ErrorAction Stop

# Pre PS 5.0
Write-Error -Exception ([System.IO.FileNotFoundException]"Could not find path: $path") -ErrorAction Stop

Write-Error -Message "Could not find path: $path" -Exception ( New-Object -TypeName System.IO.FileNotFoundException ) -ErrorAction Stop
```

Em seguida, podemos capturá-lo da seguinte maneira:

```powershell
catch [System.IO.FileNotFoundException]
{
    Write-Log $PSItem.ToString()
}
```

#### <a name="the-big-list-of-net-exceptions"></a>A grande lista de exceções do .NET

Compilei uma lista mestra com a ajuda da [Comunidade do Reddit/r/PowerShell][] que contém centenas de exceções do .NET para complementar esta postagem.

- [A grande lista de exceções do .NET][]

Começo pesquisando a lista de exceções que parecem ser adequadas para a minha situação. Você deve tentar usar exceções no namespace `System` base.

### <a name="exceptions-are-objects"></a>As exceções são objetos

Se você começar a usar muitas exceções tipadas, lembre-se de que elas são objetos. Exceções diferentes têm construtores e propriedades diferentes. Se olharmos a documentação do [FileNotFoundException][] para `System.IO.FileNotFoundException`, veremos que podemos passar uma mensagem e um caminho de arquivo.

```powershell
[System.IO.FileNotFoundException]::new("Could not find file", $path)
```

E ele tem uma propriedade `FileName` que expõe esse caminho de arquivo.

```powershell
catch [System.IO.FileNotFoundException]
{
    Write-Output $PSItem.Exception.FileName
}
```

Você deve consultar a [documentação do .NET][] para saber mais sobre outros construtores e propriedades de objeto.

### <a name="re-throwing-an-exception"></a>Como gerar novamente uma exceção

Se a única coisa que você vai fazer no seu bloco `catch` é realizar `throw` na mesma exceção, não realize `catch` nela. Você só deve realizar `catch` em uma exceção que planeja manipular ou executar alguma ação quando isso acontecer.

Há ocasiões em que você deseja executar uma ação em uma exceção, mas gera a exceção novamente para que algo em downstream possa lidar com ela. Podemos gravar uma mensagem ou registrar o problema perto de onde o descobrimos e lidar com o problema mais adiante na pilha.

```powershell
catch
{
    Write-Log $PSItem.ToString()
    throw $PSItem
}
```

Curiosamente, podemos chamar `throw` de dentro do `catch` e ele gera novamente a exceção atual.

```powershell
catch
{
    Write-Log $PSItem.ToString()
    throw
}
```

Queremos gerar novamente a exceção para preservar as informações de execução originais, como o script de origem e o número de linha. Se gerarmos uma nova exceção nesse momento, ela ocultará onde a exceção foi iniciada.

#### <a name="re-throwing-a-new-exception"></a>Como gerar novamente uma nova exceção

Se você capturar uma exceção, mas desejar gerar uma diferente, deverá aninhar a exceção original dentro da nova. Isso permite que alguém abaixo na pilha acesse-a como o `$PSItem.Exception.InnerException`.

```powershell
catch
{
    throw [System.MissingFieldException]::new('Could not access field',$PSItem.Exception)
}
```

#### <a name="pscmdletthrowterminatingerror"></a>$PSCmdlet.ThrowTerminatingError()

O que eu não gosto sobre usar `throw` para exceções brutas é que a mensagem de erro aponta para a instrução `throw` e indica que aquela linha é onde o problema está.

```Output
Unable to find the specified file.
At line:31 char:9
+         throw [System.IO.FileNotFoundException]::new()
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : OperationStopped: (:) [], FileNotFoundException
    + FullyQualifiedErrorId : Unable to find the specified file.
```

Uma mensagem de erro que informa que o meu script foi interrompido porque chamei `throw` na linha 31 é uma mensagem incorreta para ser exibida para os usuários do seu script. Ela não informa nada de útil.

Dexter Dhami apontou que posso usar `ThrowTerminatingError()` para corrigir isso.

```powershell
$PSCmdlet.ThrowTerminatingError(
    [System.Management.Automation.ErrorRecord]::new(
        ([System.IO.FileNotFoundException]"Could not find $Path"),
        'My.ID',
        [System.Management.Automation.ErrorCategory]::OpenError,
        $MyObject
    )
)
```

Se presumirmos que `ThrowTerminatingError()` foi chamado dentro de uma função chamada `Get-Resource`, esse será o erro que veremos.

```Output
Get-Resource : Could not find C:\Program Files (x86)\Reference
Assemblies\Microsoft\Framework\.NETPortable\v4.6\System.IO.xml
At line:6 char:5
+     Get-Resource -Path $Path
+     ~~~~~~~~~~~~
    + CategoryInfo          : OpenError: (:) [Get-Resource], FileNotFoundException
    + FullyQualifiedErrorId : My.ID,Get-Resource
```

Você percebe como ele aponta para a função `Get-Resource` como a origem do problema? Isso informa ao usuário algo útil.

Como `$PSItem` é um `ErrorRecord`, também podemos usar `ThrowTerminatingError` dessa maneira para gerar novamente.

```powershell
catch
{
    $PSCmdlet.ThrowTerminatingError($PSItem)
}
```

Isso altera a origem do erro para o Cmdlet e oculta os elementos internos da sua função dos usuários do seu Cmdlet.

## <a name="try-can-create-terminating-errors"></a>Try pode criar erros de encerramento

Kirk Munro destaca que algumas exceções estão encerrando erros apenas quando são executadas dentro de um bloco `try/catch`. A seguir está o exemplo que ele me deu que gera uma exceção de runtime de divisão por zero.

```powershell
function Start-Something { 1/(1-1) }
```

Em seguida, invoque-a dessa forma para que ela gere o erro e ainda gere a mensagem.

```powershell
&{ Start-Something; Write-Output "We did it. Send Email" }
```

Mas, ao colocar o mesmo código dentro de um `try/catch`, vemos outra coisa ocorrer.

```powershell
try
{
    &{ Start-Something; Write-Output "We did it. Send Email" }
}
catch
{
    Write-Output "Notify Admin to fix error and send email"
}
```

Vemos que o erro se torna um erro de encerramento e não gera a primeira mensagem. O que eu não gosto sobre isso é que você pode ter um código em uma função e ele funcionar de modo diferente se alguém estiver usando um `try/catch`.

Ainda não tive problemas com isso, mas é um caso excepcional a saber.

### <a name="pscmdletthrowterminatingerror-inside-trycatch"></a>$PSCmdlet.ThrowTerminatingError() dentro de try/catch

Uma nuance de `$PSCmdlet.ThrowTerminatingError()` é que ele cria um erro de encerramento dentro do seu Cmdlet, mas se transforma em um erro de não encerramento após sair do Cmdlet. Isso deixa a responsabilidade de decidir como tratar o erro com o chamador da sua função. Eles podem transformá-lo novamente em um erro de encerramento usando `-ErrorAction Stop` ou chamando-o de dentro de um `try{...}catch{...}`.

### <a name="public-function-templates"></a>Modelos de função pública

Uma última consideração sobre a minha conversa com Kirk Munro é que ele coloca um `try{...}catch{...}` em todos os blocos `begin`, `process` e `end` em todas as funções avançadas dele. Nesses blocos catch genéricos, uma única linha usa `$PSCmdlet.ThrowTerminatingError($PSItem)` para lidar com todas as exceções que estão saindo das funções.

```powershell
function Start-Something
{
    [CmdletBinding()]
    param()

    process
    {
        try
        {
            ...
        }
        catch
        {
            $PSCmdlet.ThrowTerminatingError($PSItem)
        }
    }
}
```

Como tudo está em uma instrução `try` nas funções dele, tudo funciona consistentemente. Isso também exibe erros de limpeza para o usuário final que oculta o código interno do erro gerado.

## <a name="trap"></a>Trap

Eu me concentrei no aspecto `try/catch` das exceções. Mas há um recurso herdado que preciso mencionar antes de terminarmos.

Um `trap` é colocado em um script ou função para capturar todas as exceções que acontecem nesse escopo. Quando ocorre uma exceção, o código no `trap` é executado e o código normal continua. Se ocorrerem várias exceções, o trap será chamado repetidamente.

```powershell
trap
{
    Write-Log $PSItem.ToString()
}

throw [System.Exception]::new('first')
throw [System.Exception]::new('second')
throw [System.Exception]::new('third')
```

Pessoalmente, nunca adotei essa abordagem, mas entendo como ela pode ser valiosa em scripts de administrador ou de controlador que registram todas as exceções e, em seguida, continuam a executar.

## <a name="closing-remarks"></a>Últimas considerações

Adicionar uma manipulação de exceção adequada aos seus scripts não só os torna mais estáveis, mas também facilita a solução de problemas dessas exceções.

Passei muito tempo falando sobre `throw` porque é um conceito fundamental ao falar sobre a manipulação de exceção. O PowerShell também nos forneceu `Write-Error` que lida com todas as situações em que você usaria `throw`. Portanto, não ache que você precisa usar `throw` depois de ler isso.

Agora que já escrevi sobre como manipular exceções nesse detalhe, vou passar a usar `Write-Error -Stop` para gerar erros no meu código. Também vou usar o conselho do Kirk e tornar o `ThrowTerminatingError` o meu manipulador de exceção padrão para cada função.

<!-- link references -->
[powershellexplained.com]: https://powershellexplained.com/
[versão original]: https://powershellexplained.com/2017-04-10-Powershell-exceptions-everything-you-ever-wanted-to-know/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[Comunidade do Reddit/r/PowerShell]: https://www.reddit.com/r/PowerShell/comments/64866o/kevmar_all_net_46_exceptions_list_for_use_with/
[A grande lista de exceções do .NET]: https://powershellexplained.com/2017-04-07-all-dotnet-exception-list
[FileNotFoundException]: https://docs.microsoft.com/dotnet/api/System.IO.FileNotFoundException
[Documentação do .NET]: https://docs.microsoft.com/dotnet/api
