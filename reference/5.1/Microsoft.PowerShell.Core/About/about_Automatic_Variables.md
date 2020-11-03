---
description: Descreve as variáveis que armazenam informações de estado do PowerShell. Essas variáveis são criadas e mantidas pelo PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 08/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_automatic_variables?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Automatic_Variables
ms.openlocfilehash: d56e844bd10dfffabb1d2cfd75bcfe113724a334
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196039"
---
# <a name="about-automatic-variables"></a>Sobre variáveis automáticas

## <a name="short-description"></a>Descrição breve

Descreve as variáveis que armazenam informações de estado do PowerShell. Essas variáveis são criadas e mantidas pelo PowerShell.

## <a name="long-description"></a>Descrição longa

Conceitualmente, essas variáveis são consideradas como somente leitura. Embora eles **possam** ser gravados, para compatibilidade com versões anteriores, eles **não devem** ser gravados.

Aqui está uma lista das variáveis automáticas no PowerShell:

### <a name=""></a>$$

Contém o último token na última linha recebida pela sessão.

### <a name=""></a>$?

Contém o status de execução do último comando. Ele conterá **true** se o último comando tiver êxito e **false** se ele tiver falhado.

Para cmdlets e funções avançadas que são executadas em vários estágios em um pipeline, por exemplo, em `process` `end` blocos and, chamando `this.WriteError()` ou `$PSCmdlet.WriteError()` respectivamente em qualquer ponto, serão definidos como `$?` **false** , como `this.ThrowTerminatingError()` e `$PSCmdlet.ThrowTerminatingError()` .

O `Write-Error` cmdlet sempre define `$?` como **false** imediatamente após ser executado, mas não será definido `$?` como **false** para uma função que a chama:

```powershell
function Test-WriteError
{
    Write-Error "Bad"
    $? # $false
}

Test-WriteError
$? # $true
```

Para a última finalidade, `$PSCmdlet.WriteError()` deve ser usado em vez disso.

Para comandos nativos (executáveis), `$?` é definido como **true** quando `$LASTEXITCODE` é 0 e definido como **false** quando `$LASTEXITCODE` é qualquer outro valor.

> [!NOTE]
> Até o PowerShell 7, que contém uma instrução entre parênteses `(...)` , sintaxe `$(...)` de subexpressão ou expressão `@(...)` de matriz sempre redefinida como `$?` **true** , para que seja `(Write-Error)` exibida `$?` como **verdadeira** .
> Isso foi alterado no PowerShell 7, de modo que `$?` sempre refletirá o êxito real da execução do último comando nessas expressões.

### <a name=""></a>$^

Contém o primeiro token na última linha recebida pela sessão.

### <a name="_"></a>$_

Mesmo que `$PSItem`. Contém o objeto atual no objeto de pipeline. Você pode usar essa variável em comandos que executam uma ação em cada objeto ou em objetos selecionados em um pipeline.

### <a name="args"></a>$args

Contém uma matriz de valores para parâmetros não declarados que são passados para uma função, script ou bloco de script. Ao criar uma função, você pode declarar os parâmetros usando a `param` palavra-chave ou adicionando uma lista separada por vírgulas de parâmetros entre parênteses após o nome da função.

Em uma ação de evento, a `$Args` variável contém objetos que representam os argumentos do evento que está sendo processado. Essa variável é populada somente dentro do `Action` bloco de um comando de registro de evento.
O valor dessa variável também pode ser encontrado na propriedade **SourceArgs** do objeto **PSEventArgs** que `Get-Event` retorna.

### <a name="consolefilename"></a>$ConsoleFileName

Contém o caminho do arquivo de console ( `.psc1` ) que foi usado mais recentemente na sessão. Essa variável é populada quando você inicia o PowerShell com o parâmetro **PSConsoleFile** ou quando usa o `Export-Console` cmdlet para exportar nomes de snap-in para um arquivo de console.

Quando você usa o `Export-Console` cmdlet sem parâmetros, ele atualiza automaticamente o arquivo de console que foi usado mais recentemente na sessão. Você pode usar essa variável automática para determinar qual arquivo será atualizado.

### <a name="error"></a>$Error

Contém uma matriz de objetos de erro que representam os erros mais recentes.
O erro mais recente é o primeiro objeto de erro na matriz `$Error[0]` .

Para impedir que um erro seja adicionado à `$Error` matriz, use o parâmetro comum **ErrorAction** com um valor de **ignorar** . Para obter mais informações, confira [about_CommonParameters](about_CommonParameters.md).

### <a name="event"></a>$Event

Contém um objeto **PSEventArgs** que representa o evento que está sendo processado. Essa variável é populada somente dentro do `Action` bloco de um comando de registro de evento, como `Register-ObjectEvent` . O valor dessa variável é o mesmo objeto que o `Get-Event` cmdlet retorna. Portanto, você pode usar as propriedades da `Event` variável, como `$Event.TimeGenerated` , em um bloco de `Action` script.

### <a name="eventargs"></a>$EventArgs

Contém um objeto que representa o primeiro argumento de evento que deriva de **EventArgs** do evento que está sendo processado. Essa variável é populada somente dentro do `Action` bloco de um comando de registro de evento.
O valor dessa variável também pode ser encontrado na propriedade **SourceEventArgs** do objeto **PSEventArgs** que `Get-Event` retorna.

### <a name="eventsubscriber"></a>$EventSubscriber

Contém um objeto **PSEventSubscriber** que representa o Assinante de evento do evento que está sendo processado. Essa variável é populada somente dentro do `Action` bloco de um comando de registro de evento. O valor dessa variável é o mesmo objeto que o `Get-EventSubscriber` cmdlet retorna.

### <a name="executioncontext"></a>$ExecutionContext

Contém um objeto **EngineIntrinsics** que representa o contexto de execução do host do PowerShell. Você pode usar essa variável para localizar os objetos de execução que estão disponíveis para os cmdlets.

### <a name="false"></a>$false

Contém **false** . Você pode usar essa variável para representar **falso** em comandos e scripts em vez de usar a cadeia de caracteres "false". A cadeia de caracteres poderá ser interpretada como **true** se for convertida em uma cadeia de caracteres não vazia ou em um inteiro diferente de zero.

### <a name="foreach"></a>$foreach

Contém o enumerador (não os valores resultantes) de um loop [foreach](about_ForEach.md) . A `$ForEach` variável existe somente enquanto o `ForEach` loop está em execução; ela é excluída após a conclusão do loop.

Enumeradores contêm propriedades e métodos que você pode usar para recuperar valores de loop e alterar a iteração do loop atual. Para obter mais informações, consulte [usando enumeradores](#using-enumerators).

### <a name="home"></a>$HOME

Contém o caminho completo do diretório base do usuário. Essa variável é equivalente às variáveis de `"$env:homedrive$env:homepath"` ambiente do Windows, normalmente `C:\Users\<UserName>` .

### <a name="host"></a>$Host

Contém um objeto que representa o aplicativo host atual para o PowerShell. Você pode usar essa variável para representar o host atual em comandos ou para exibir ou alterar as propriedades do host, como `$Host.version` ou ou `$Host.CurrentCulture` `$host.ui.rawui.setbackgroundcolor("Red")` .

### <a name="input"></a>$input

Contém um enumerador que enumera todas as entradas passadas para uma função. A `$input` variável está disponível somente para funções e blocos de script (que são funções sem nome).

- Em uma função sem um `Begin` `Process` bloco, ou `End` , a `$input` variável enumera a coleção de todas as entradas para a função.

- No `Begin` bloco, a `$input` variável não contém dados.

- No `Process` bloco, a `$input` variável contém o objeto que está atualmente no pipeline.

- No `End` bloco, a `$input` variável enumera a coleção de todas as entradas para a função.

  > [!NOTE]
  > Não é possível usar a `$input` variável dentro do bloco Process e do bloco end na mesma função ou bloco de script.

Como `$input` é um enumerador, o acesso a qualquer uma das suas propriedades faz com que `$input` não esteja mais disponível. Você pode armazenar `$input` em outra variável para reutilizar as `$input` Propriedades.

Enumeradores contêm propriedades e métodos que você pode usar para recuperar valores de loop e alterar a iteração do loop atual. Para obter mais informações, consulte [usando enumeradores](#using-enumerators).


### <a name="lastexitcode"></a>$LastExitCode

Contém o código de saída do último programa baseado no Windows que foi executado.

### <a name="matches"></a>$Matches

A `Matches` variável funciona com os `-match` `-notmatch` operadores e.
Quando você envia a entrada escalar para `-match` o `-notmatch` operador OR e qualquer uma detecta uma correspondência, elas retornam um valor booliano e preenchem a `$Matches` variável automática com uma tabela de hash de quaisquer valores de cadeia de caracteres que foram correspondidos. A `$Matches` tabela de hash também pode ser populada com capturas quando você usa expressões regulares com o `-match` operador.

Para obter mais informações sobre o `-match` operador, consulte [about_Comparison_Operators](about_comparison_operators.md). Para obter mais informações sobre expressões regulares, consulte [about_Regular_Expressions](about_Regular_Expressions.md).

### <a name="myinvocation"></a>$MyInvocation

Contém informações sobre o comando atual, como nome, parâmetros, valores de parâmetro e informações sobre como o comando foi iniciado, chamado ou invocado, como o nome do script que chamou o comando atual.

`$MyInvocation` é preenchido somente para scripts, funções e blocos de script. Você pode usar as informações no objeto **System. Management. Automation. InvocationInfo** que `$MyInvocation` retorna no script atual, como o caminho e o nome do arquivo do script ( `$MyInvocation.MyCommand.Path` ) ou o nome de uma função ( `$MyInvocation.MyCommand.Name` ) para identificar o comando atual. Isso é particularmente útil para localizar o nome do script atual.

A partir do PowerShell 3,0, `MyInvocation` o tem as novas propriedades a seguir.

| Propriedade      | Descrição                                         |
| ------------- | --------------------------------------------------- |
| **PSScriptRoot**  | Contém o caminho completo para o script que foi invocado   |
|               | o comando atual. O valor dessa propriedade é  |
|               | populado somente quando o chamador é um script.         |
| **PSCommandPath** | Contém o caminho completo e o nome do arquivo do script  |
|               | que invocou o comando atual. O valor deste |
|               | a propriedade é populada somente quando o chamador é um     |
|               | .                                             |

Ao contrário `$PSScriptRoot` das `$PSCommandPath` variáveis e automáticas, as propriedades **PSScriptRoot** e **PSCommandPath** da `$MyInvocation` variável automática contêm informações sobre o chamador ou o script de chamada, não o script atual.

### <a name="nestedpromptlevel"></a>$NestedPromptLevel

Contém o nível do prompt atual. Um valor de 0 indica o nível do prompt original. O valor é incrementado quando você insere um nível aninhado e diminui quando sai dele.

Por exemplo, o PowerShell apresenta um prompt de comando aninhado quando você usa o `$Host.EnterNestedPrompt` método. O PowerShell também apresenta um prompt de comando aninhado quando você atinge um ponto de interrupção no depurador do PowerShell.

Quando você insere um prompt aninhado, o PowerShell pausa o comando atual, salva o contexto de execução e incrementa o valor da `$NestedPromptLevel` variável. Para criar prompts de comando aninhados adicionais (até 128 níveis) ou retornar ao prompt de comando original, conclua o comando ou digite `exit` .

A `$NestedPromptLevel` variável ajuda a acompanhar o nível do prompt. Você pode criar um prompt de comando alternativo do PowerShell que inclua esse valor para que ele fique sempre visível.

### <a name="null"></a>$null

`$null` é uma variável automática que contém um valor **nulo** ou vazio. Você pode usar essa variável para representar um valor ausente ou indefinido em comandos e scripts.

O PowerShell trata `$null` como um objeto com um valor, ou seja, como um espaço reservado explícito, para que você possa usar `$null` para representar um valor vazio em uma série de valores.

Por exemplo, quando `$null` é incluído em uma coleção, ele é contado como um dos objetos.

```powershell
$a = "one", $null, "three"
$a.count
```

```Output
3
```

Se você canalizar a `$null` variável para o `ForEach-Object` cmdlet, ele gerará um valor para `$null` , assim como faz para os outros objetos

```powershell
"one", $null, "three" | ForEach-Object { "Hello " + $_}
```

```Output
Hello one
Hello
Hello three
```

Como resultado, você não pode usar `$null` para significar **nenhum valor de parâmetro** . Um valor de parâmetro de `$null` substitui o valor de parâmetro padrão.

No entanto, como o PowerShell trata a `$null` variável como um espaço reservado, você pode usá-la em scripts como o seguinte, o que não funcionaria se `$null` fosse ignorado.

```powershell
$calendar = @($null, $null, "Meeting", $null, $null, "Team Lunch", $null)
$days = "Sunday","Monday","Tuesday","Wednesday","Thursday",
        "Friday","Saturday"
$currentDay = 0
foreach($day in $calendar)
{
    if($day -ne $null)
    {
        "Appointment on $($days[$currentDay]): $day"
    }

    $currentDay++
}
```

```Output
Appointment on Tuesday: Meeting
Appointment on Friday: Team lunch
```

### <a name="pid"></a>$PID

Contém o identificador do processo (PID) do processo que está hospedando a sessão atual do PowerShell.

### <a name="profile"></a>$PROFILE

Contém o caminho completo do perfil do PowerShell para o usuário atual e o aplicativo host atual. Você pode usar essa variável para representar o perfil em comandos. Por exemplo, você pode usá-lo em um comando para determinar se um perfil foi criado:

```powershell
Test-Path $PROFILE
```

Ou você pode usá-lo em um comando para criar um perfil:

```powershell
New-Item -ItemType file -Path $PROFILE -Force
```

Você pode usá-lo em um comando para abrir o perfil no **notepad.exe** :

```powershell
notepad.exe $PROFILE
```

### <a name="psboundparameters"></a>$PSBoundParameters

Contém um dicionário dos parâmetros que são passados para um script ou função e seus valores atuais. Essa variável tem um valor somente em um escopo em que os parâmetros são declarados, como um script ou uma função. Você pode usá-lo para exibir ou alterar os valores atuais dos parâmetros ou para passar valores de parâmetro para outro script ou função.

Neste exemplo, a função **test2** passa o `$PSBoundParameters` para a função **Test1** . Os `$PSBoundParameters` são exibidos no formato de **chave** e **valor** .

```powershell
function Test1 {
   param($a, $b)

   # Display the parameters in dictionary format.
   $PSBoundParameters
}

function Test2 {
   param($a, $b)

   # Run the Test1 function with $a and $b.
   Test1 @PSBoundParameters
}
```

```powershell
Test2 -a Power -b Shell
```

```Output
Key   Value
---   -----
a     Power
b     Shell
```

### <a name="pscmdlet"></a>$PSCmdlet

Contém um objeto que representa o cmdlet ou a função avançada que está sendo executada.

Você pode usar as propriedades e os métodos do objeto no seu cmdlet ou código de função para responder às condições de uso. Por exemplo, a propriedade **ParameterSetName** contém o nome do conjunto de parâmetros que está sendo usado, e o método **ShouldProcess** adiciona os parâmetros **WhatIf** e **Confirm** ao cmdlet dinamicamente.

Para obter mais informações sobre a `$PSCmdlet` variável automática, consulte [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md) e [about_Functions_Advanced](about_Functions_Advanced.md).

### <a name="pscommandpath"></a>$PSCommandPath

Contém o caminho completo e o nome de arquivo do script que está sendo executado. Essa variável é válida em todos os scripts.

### <a name="psculture"></a>$PSCulture

Contém o nome da cultura atualmente em uso no sistema operacional. A cultura determina o formato de exibição de itens, como números, moeda e datas, e é armazenado em um objeto **System. Globalization. CultureInfo** . Use `Get-Culture` para exibir a cultura do computador. `$PSCulture` contém o valor da propriedade de **nome** .

### <a name="psdebugcontext"></a>$PSDebugContext

Durante a depuração, essa variável contém informações sobre o ambiente de depuração. Caso contrário, ele contém um valor **nulo** . Como resultado, você pode usá-lo para indicar se o depurador tem controle. Quando preenchido, ele contém um objeto **PSDebugContext** que tem **pontos de interrupção** e propriedades **InvocationInfo** . A propriedade **InvocationInfo** tem várias propriedades úteis, incluindo a propriedade **Location** . A propriedade **Location** indica o caminho do script que está sendo depurado.

### <a name="pshome"></a>$PSHOME

Contém o caminho completo do diretório de instalação do PowerShell, normalmente, `$env:windir\System32\PowerShell\v1.0` em sistemas Windows. Você pode usar essa variável nos caminhos de arquivos do PowerShell. Por exemplo, o comando a seguir pesquisa os tópicos de ajuda conceitual para a **variável** de palavra:

```powershell
Select-String -Pattern Variable -Path $pshome\*.txt
```

### <a name="psitem"></a>$PSItem

Mesmo que `$_`. Contém o objeto atual no objeto de pipeline. Você pode usar essa variável em comandos que executam uma ação em cada objeto ou em objetos selecionados em um pipeline.

### <a name="psscriptroot"></a>$PSScriptRoot

Contém o diretório do qual um script está sendo executado.

No PowerShell 2,0, essa variável é válida somente em módulos de script ( `.psm1` ).
A partir do PowerShell 3,0, ele é válido em todos os scripts.

### <a name="pssenderinfo"></a>$PSSenderInfo

Contém informações sobre o usuário que iniciou a PSSession, incluindo a identidade do usuário e o fuso horário do computador de origem. Essa variável está disponível somente em PSSessions.

A `$PSSenderInfo` variável inclui uma propriedade configurável pelo usuário, **ApplicationArguments** , que, por padrão, contém apenas o `$PSVersionTable` da sessão de origem. Para adicionar dados à propriedade **ApplicationArguments** , use o parâmetro **ApplicationArguments** do `New-PSSessionOption` cmdlet.

### <a name="psuiculture"></a>$PSUICulture

Contém o nome da cultura da interface do usuário que está atualmente em uso no sistema operacional. A cultura da interface do usuário determina quais cadeias de caracteres de texto são usadas para elementos de interface do usuário, como menus e mensagens. Esse é o valor da propriedade **System.Globalization.CultureInfo.CurrentUICulture.Name** do sistema. Para obter o objeto **System. Globalization. CultureInfo** do sistema, use o `Get-UICulture` cmdlet.

### <a name="psversiontable"></a>$PSVersionTable

Contém uma tabela de hash somente leitura que exibe detalhes sobre a versão do PowerShell que está sendo executada na sessão atual. A tabela inclui os seguintes itens:

| Propriedade                  | Descrição                                   |
| ------------------------- | --------------------------------------------- |
| **BuildVersion**          | O número de Build da versão atual       |
| **CLRVersion**            | A versão do Common Language Runtime    |
|                           | CLR                                         |
| **PSCompatibleVersions**  | Versões do PowerShell que são compatíveis    |
|                           | com a versão atual                      |
| **PSEdition**             | Esta propriedade tem o valor de ' Desktop ', para |
|                           | Versões do Windows Server e do cliente do Windows.   |
|                           | Esta propriedade tem o valor de ' Core ' para     |
|                           | PowerShell em execução no nano Server ou       |
|                           | IOT do Windows.                                  |
| **PSRemotingProtocolVersion** | A versão do PowerShell remoto      |
|                           | Protocolo de gerenciamento.                          |
| **PSVersion**             | O número de versão do PowerShell                 |
| **SerializationVersion**  | A versão do método de serialização       |
| **WSManStackVersion**     | O número de versão da pilha de WS-Management |

### <a name="pwd"></a>$PWD

Contém um objeto Path que representa o caminho completo do diretório atual.

### <a name="sender"></a>$Sender

Contém o objeto que gerou este evento. Essa variável é populada somente dentro do bloco de ação de um comando de registro de evento. O valor dessa variável também pode ser encontrado na propriedade Sender do objeto **PSEventArgs** que `Get-Event` retorna.

### <a name="shellid"></a>$ShellId

Contém o identificador do shell atual.

### <a name="stacktrace"></a>$StackTrace

Contém um rastreamento de pilha para o erro mais recente.

### <a name="switch"></a>$switch

Contém o enumerador não os valores resultantes de uma `Switch` instrução. A `$switch` variável existe somente enquanto a `Switch` instrução está em execução; ela é excluída quando a `switch` instrução conclui a execução. Para obter mais informações, consulte [about_Switch](about_Switch.md).

Enumeradores contêm propriedades e métodos que você pode usar para recuperar valores de loop e alterar a iteração do loop atual. Para obter mais informações, consulte [usando enumeradores](#using-enumerators).

### <a name="this"></a>$this

Em um bloco de script que define uma propriedade de script ou um método de script, a `$this` variável refere-se ao objeto que está sendo estendido.

Em uma classe personalizada, a `$this` variável refere-se ao próprio objeto de classe, permitindo o acesso a propriedades e métodos definidos na classe.

### <a name="true"></a>$true

Contém **true** . Você pode usar essa variável para representar **true** em comandos e scripts.

## <a name="using-enumerators"></a>Usando enumeradores

As `$input` `$foreach` variáveis, e `$switch` são todos os enumeradores usados para iterar pelos valores processados pelo bloco de código que o contém.

Um enumerador contém propriedades e métodos que você pode usar para avançar ou redefinir a iteração ou recuperar valores de iteração. Os enumeradores de manipulação direta não são considerados práticas recomendadas.

- Em loops, as palavras-chave de controle de fluxo [quebram](about_Break.md) e [continuam](about_Continue.md) como preferíveis.
- Em funções que aceitam a entrada de pipeline, é recomendável usar parâmetros com os atributos **ValueFromPipeline** ou **valueFromPipelineByPropertyName** .

  Para obter mais informações, consulte [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).

### <a name="movenext"></a>MoveNext

O método [MoveNext](/dotnet/api/system.collections.ienumerator.movenext) avança o enumerador para o próximo elemento da coleção. **MoveNext** retornará **true** se o enumerador tiver sido avançado com êxito; **false** se o enumerador tiver passado o final da coleção.

> [!NOTE]
> O valor **booliano** retornou meu **MoveNext** é enviado para o fluxo de saída.
> Você pode suprimir a saída ao typecasting-la `[void]` ou canaliza-la para [out-null](xref:Microsoft.PowerShell.Core.Out-Null).
>
> ```powershell
> $input.MoveNext() | Out-Null
> ```
>
> ```powershell
> [void]$input.MoveNext()
> ```

### <a name="reset"></a>Redefinir

O método [Reset](/dotnet/api/system.collections.ienumerator.reset) define o enumerador para sua posição inicial, que é **antes** do primeiro elemento na coleção.

### <a name="current"></a>Current

A propriedade [Current](/dotnet/api/system.collections.ienumerator.current) Obtém o elemento na coleção, ou pipeline, na posição atual do enumerador.

A propriedade **Current** continua retornando a mesma propriedade até que **MoveNext** seja chamado.

## <a name="examples"></a>Exemplos

### <a name="example-1-using-the-input-variable"></a>Exemplo 1: usando a variável $input

No exemplo a seguir, o acesso à `$input` variável limpa a variável até a próxima vez que o bloco de processo for executado. O uso do método **Redefinir** redefine a `$input` variável para o valor do pipeline atual.

```powershell
function Test
{
    begin
    {
        $i = 0
    }

    process
    {
        "Iteration: $i"
        $i++
        "`tInput: $input"
        "`tAccess Again: $input"
        $input.Reset()
        "`tAfter Reset: $input"
    }
}

"one","two" | Test
```

```Output
Iteration: 0
    Input: one
    Access Again:
    After Reset: one
Iteration: 1
    Input: two
    Access Again:
    After Reset: two
```

O bloco de processo avança automaticamente a `$input` variável mesmo se você não acessá-la.

```powershell
$skip = $true
function Skip
{
    begin
    {
        $i = 0
    }

    process
    {
        "Iteration: $i"
        $i++
        if ($skip)
        {
            "`tSkipping"
            $skip = $false
        }
        else
        {
            "`tInput: $input"
        }
    }
}

"one","two" | Skip
```

```Output
Iteration: 0
    Skipping
Iteration: 1
    Input: two
```

### <a name="example-2-using-input-outside-the-process-block"></a>Exemplo 2: usando $input fora do bloco de processo

Fora do bloco de processo, a `$input` variável representa todos os valores canalizados para a função.

- O acesso à `$input` variável limpa todos os valores.
- O método de **redefinição** redefine a coleção inteira.
- A propriedade **atual** nunca é populada.
- O método **MoveNext** retorna false porque a coleção não pode ser avançada.
  - Chamar **MoveNext** limpa a `$input` variável.

```powershell
Function All
{
    "All Values: $input"
    "Access Again: $input"
    $input.Reset()
    "After Reset: $input"
    $input.MoveNext() | Out-Null
    "After MoveNext: $input"
}

"one","two","three" | All
```

```Output
All Values: one two three
Access Again:
After Reset: one two three
After MoveNext:
```

### <a name="example-3-using-the-inputcurrent-property"></a>Exemplo 3: usando o $input. Propriedade atual

Usando a propriedade **Current** , o valor do pipeline atual pode ser acessado várias vezes sem usar o método **Reset** . O bloco de processo não chama automaticamente o método **MoveNext** .

A propriedade **atual** nunca será preenchida a menos que você chame explicitamente **MoveNext** . A propriedade **Current** pode ser acessada várias vezes dentro do bloco Process sem limpar seu valor.

```powershell
function Current
{
    begin
    {
        $i = 0
    }

    process
    {
        "Iteration: $i"
        $i++
        "`tBefore MoveNext: $($input.Current)"
        $input.MoveNext() | Out-Null
        "`tAfter MoveNext: $($input.Current)"
        "`tAccess Again: $($input.Current)"
    }
}

"one","two" | Current
```

```Output
Iteration: 0
    Before MoveNext:
    After MoveNext: one
    Access Again: one
Iteration: 1
    Before MoveNext:
    After MoveNext: two
    Access Again: two
```

### <a name="example-4-using-the-foreach-variable"></a>Exemplo 4: usando a variável $foreach

Ao contrário da `$input` variável, a `$foreach` variável sempre representa todos os itens na coleção quando acessados diretamente. Use a propriedade **Current** para acessar o elemento da coleção atual e os métodos **Reset** e **MoveNext** para alterar seu valor.

> [!NOTE]
> Cada iteração do `foreach` loop chamará automaticamente o método **MoveNext** .

O loop a seguir é executado duas vezes. Na segunda iteração, a coleção é movida para o terceiro elemento antes da conclusão da iteração. Após a segunda iteração, agora não há mais valores para iterar e o loop é encerrado.

A propriedade **MoveNext** não afeta a variável escolhida para iterar pela coleção ( `$Num` ).

```powershell
$i = 0
foreach ($num in ("one","two","three"))
{
    "Iteration: $i"
    $i++
    "`tNum: $num"
    "`tCurrent: $($foreach.Current)"

    if ($foreach.Current -eq "two")
    {
        "Before MoveNext (Current): $($foreach.Current)"
        $foreach.MoveNext() | Out-Null
        "After MoveNext (Current): $($foreach.Current)"
        "Num has not changed: $num"
    }
}
```

```Output
Iteration: 0
        Num: one
        Current: one
Iteration: 1
        Num: two
        Current: two
Before MoveNext (Current): two
After MoveNext (Current): three
Num has not changed: two
```

O uso do método **Redefinir** redefine o elemento atual na coleção. O exemplo a seguir faz um loop pelos dois primeiros elementos **duas vezes** porque o método **Reset** é chamado. Após os dois primeiros loops, a `if` instrução falha e o loop é iterado por todos os três elementos normalmente.

> [!IMPORTANT]
> Isso pode resultar em um loop infinito.

```powershell
$stopLoop = 0
foreach ($num in ("one","two", "three"))
{
    ("`t" * $stopLoop) + "Current: $($foreach.Current)"

    if ($num -eq "two" -and $stopLoop -lt 2)
    {
        $foreach.Reset() | Out-Null
        ("`t" * $stopLoop) + "Reset Loop: $stopLoop"
        $stopLoop++
    }
}
```

```Output
Current: one
Current: two
Reset Loop: 0
        Current: one
        Current: two
        Reset Loop: 1
                Current: one
                Current: two
                Current: three
```

### <a name="example-5-using-the-switch-variable"></a>Exemplo 5: usando a variável $switch

A `$switch` variável tem exatamente as mesmas regras que a `$foreach` variável.
O exemplo a seguir demonstra todos os conceitos de enumerador.

> [!NOTE]
> Observe como o caso não **avaliado** nunca é executado, mesmo que não haja `break` instrução após o método **MoveNext** .

```powershell
$values = "Start", "MoveNext", "NotEvaluated", "Reset", "End"
$stopInfinite = $false
switch ($values)
{
    "MoveNext" {
        "`tMoveNext"
        $switch.MoveNext() | Out-Null
        "`tAfter MoveNext: $($switch.Current)"
    }
    # This case is never evaluated.
    "NotEvaluated" {
        "`tAfterMoveNext: $($switch.Current)"
    }

    "Reset" {
        if (!$stopInfinite)
        {
            "`tReset"
            $switch.Reset()
            $stopInfinite = $true
        }
    }

    default {
        "Default (Current): $($switch.Current)"
    }
}
```

```Output
Default (Current): Start
    MoveNext
    After MoveNext: NotEvaluated
    Reset
Default (Current): Start
    MoveNext
    After MoveNext: NotEvaluated
Default (Current): End
```

## <a name="see-also"></a>Confira também

[about_Functions](about_Functions.md)

[about_Functions_Advanced](about_Functions_Advanced.md)

[about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md)

[about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)

[about_Functions_OutputTypeAttribute](about_Functions_OutputTypeAttribute.md)

[about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md)

[about_Hash_Tables](about_Hash_Tables.md)

[about_Preference_Variables](about_Preference_Variables.md)

[about_Splatting](about_Splatting.md)

[about_Variables](about_Variables.md)
