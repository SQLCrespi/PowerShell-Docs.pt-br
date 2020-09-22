---
title: Tudo o que você queria saber sobre o ShouldProcess
description: O ShouldProcess é um recurso importante, mas que muitas vezes é ignorado. Com os parâmetros WhatIf e Confirm, fica fácil adicioná-lo às funções.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 6bd4dbd5255203f2daf804163aa2a84d992d6697
ms.sourcegitcommit: 0afff6edbe560e88372dd5f1cdf51d77f9349972
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/20/2020
ms.locfileid: "86469728"
---
# <a name="everything-you-wanted-to-know-about-shouldprocess"></a>Tudo o que você queria saber sobre o ShouldProcess

As funções do PowerShell têm vários recursos que aprimoram muito a interação com os usuários.
Um recurso importante, mas que muitas vezes é ignorado é o suporte para `-WhatIf` e `-Confirm`, e é muito fácil adicioná-lo às funções. Neste artigo, vamos nos aprofundar em como implementar esse recurso.

> [!NOTE]
> A [versão original][] deste artigo foi publicada no blog escrito por [@KevinMarquette][]. A equipe do PowerShell agradece a Kevin por compartilhar o conteúdo conosco. Confira o blog dele em [PowerShellExplained.com][].

É um recurso simples e que você pode habilitar nas funções para fornecer uma rede de segurança aos usuários que precisarem. Não há nada mais assustador do que executar um comando que você sabe que pode ser perigoso pela primeira vez. A opção de executá-lo com `-WhatIf` pode fazer muita diferença.

## <a name="commonparameters"></a>CommonParameters

Antes de vermos como implementar esses [parâmetros comuns][], vamos dar uma olhada em como eles são usados.

## <a name="using--whatif"></a>Usando o -WhatIf

Quando um comando dá suporte ao parâmetro `-WhatIf`, ele permite que você veja o que o comando teria feito em vez de fazer as alterações. Essa é uma boa maneira de testar o impacto de um comando, especialmente antes de fazer algo destrutivo.

```powershell
PS C:\temp> Remove-Item -Path .\myfile1.txt -WhatIf
What if: Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
```

Se o comando implementar corretamente `ShouldProcess`, ele mostrará todas as alterações que teria feito. Aqui está um exemplo que usa um curinga para excluir vários arquivos.

```powershell
PS C:\temp> Remove-Item -Path * -WhatIf
What if: Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
What if: Performing the operation "Remove File" on target "C:\Temp\myfile2.txt".
What if: Performing the operation "Remove File" on target "C:\Temp\importantfile.txt".
```

## <a name="using--confirm"></a>Usando o -Confirm

Comandos que oferecem suporte ao `-WhatIf` também oferecem suporte ao `-Confirm`. Isso dá a você a chance de confirmar uma ação antes de executá-la.

```powershell
PS C:\temp> Remove-Item .\myfile1.txt -Confirm

Confirm
Are you sure you want to perform this action?
Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

Nesse caso, você tem várias opções que permitem continuar, ignorar uma alteração ou parar o script. O prompt de ajuda descreve cada uma dessas opções assim.

```Output
Y - Continue with only the next step of the operation.
A - Continue with all the steps of the operation.
N - Skip this operation and proceed with the next operation.
L - Skip this operation and all subsequent operations.
S - Pause the current pipeline and return to the command prompt. Type "exit" to resume the pipeline.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

### <a name="localization"></a>Localização

Esse prompt é localizado no PowerShell para que o idioma seja alterado com base no idioma do sistema operacional. Essa é mais uma das coisas que o PowerShell gerencia para você.

### <a name="switch-parameters"></a>Parâmetros de opção

Vejamos rapidamente algumas maneiras de como passar um valor para um parâmetro de opção. O principal motivo pelo qual eu enfatizo isso é que, muitas vezes, você deseja passar valores de parâmetro para as funções que chama.

A primeira abordagem é uma sintaxe de parâmetro específica que pode ser usada para todos os parâmetros, mas que é usada principalmente para parâmetros de switch. Você especifica dois-pontos para anexar um valor ao parâmetro.

```powershell
Remove-Item -Path:* -WhatIf:$true
```

Você pode fazer o mesmo com uma variável.

```powershell
$DoWhatIf = $true
Remove-Item -Path * -WhatIf:$DoWhatIf
```

A segunda abordagem é usar uma tabela de hash para nivelar o valor.

```powershell
$RemoveSplat = @{
    Path = '*'
    WhatIf = $true
}
Remove-Item @RemoveSplat
```

Caso você seja um novato em tabelas de hash ou nivelamento, escrevi outro artigo sobre isso que aborda [tudo o que você queria saber sobre as tabelas de hash][].

## <a name="supportsshouldprocess"></a>SupportsShouldProcess

A primeira etapa para habilitar o suporte a `-WhatIf` e `-Confirm` é especificar `SupportsShouldProcess` no `CmdletBinding` da função.

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()
    Remove-Item .\myfile1.txt
}
```

Ao especificar `SupportsShouldProcess` dessa forma, podemos chamar nossa função com `-WhatIf` (ou `-Confirm`).

```powershell
PS> Test-ShouldProcess -WhatIf
What if: Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
```

Observe que eu não criei um parâmetro chamado `-WhatIf`. Ao especificar `SupportsShouldProcess`, ele é automaticamente o criado para nós. Quando especificamos o parâmetro `-WhatIf` no `Test-ShouldProcess`, algumas coisas que chamamos também executam o processamento `-WhatIf`.

### <a name="trust-but-verify"></a>Confiar sem deixar de verificar

Há certo perigo em confiar que tudo o que você chama herdará valores `-WhatIf`. Para o restante dos exemplos, vou supor que não funcionará assim e serei bastante explícito ao fazer chamadas para outros comandos. Recomendo que você faça o mesmo.

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()
    Remove-Item .\myfile1.txt -WhatIf:$WhatIf
}
```

Revisitarei as nuances mais tarde, quando você já você tiver uma compreensão melhor de todas as peças em jogo.

## <a name="pscmdletshouldprocess"></a>$PSCmdlet.ShouldProcess

O método que permite implementar `SupportsShouldProcess` é `$PSCmdlet.ShouldProcess`. Você chama `$PSCmdlet.ShouldProcess(...)` para ver se deve processar alguma lógica e o PowerShell cuida do resto. Vamos começar com um exemplo:

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()

    $file = Get-ChildItem './myfile1.txt'
    if($PSCmdlet.ShouldProcess($file.Name)){
        $file.Delete()
    }
}
```

A chamada para `$PSCmdlet.ShouldProcess($file.name)` verifica a `-WhatIf` (e o parâmetro `-Confirm`) e então a manipula adequadamente. O `-WhatIf` faz com que `ShouldProcess` gere uma descrição da alteração e retorne `$false`:

```powershell
PS> Test-ShouldProcess -WhatIf
What if: Performing the operation "Test-ShouldProcess" on target "myfile1.txt".
```

Uma chamada usando `-Confirm` pausa o script e solicita ao usuário a opção de continuar. Ele retornará `$true` se o usuário tiver selecionado `Y`.

```powershell
PS> Test-ShouldProcess -Confirm
Confirm
Are you sure you want to perform this action?
Performing the operation "Test-ShouldProcess" on target "myfile1.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

Um recurso incrível do `$PSCmdlet.ShouldProcess` é que ele dobra como saída detalhada. Eu frequentemente recorro a isso ao implementar `ShouldProcess`.

```powershell
PS> Test-ShouldProcess -Verbose
VERBOSE: Performing the operation "Test-ShouldProcess" on target "myfile1.txt".
```

### <a name="overloads"></a>Sobrecargas

Há algumas sobrecargas diferentes para `$PSCmdlet.ShouldProcess` com parâmetros diferentes para personalizar as mensagens. Já vimos a primeira no exemplo acima. Vamos examinar cada uma mais detalhadamente.

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()

    if($PSCmdlet.ShouldProcess('TARGET')){
        # ...
    }
}
```

Isso produz a saída que inclui o nome da função e o destino (valor do parâmetro).

```powershell
What if: Performing the operation "Test-ShouldProcess" on target "TARGET".
```

Ao especificar um segundo parâmetro como a operação, o valor da operação é usado em vez do nome da função na mensagem.

```powershell
## $PSCmdlet.ShouldProcess('TARGET','OPERATION')
What if: Performing the operation "OPERATION" on target "TARGET".
```

A próxima opção é especificar três parâmetros para personalizar a mensagem. Quando três parâmetros são usados, o primeiro é a mensagem inteira. Os dois parâmetros seguintes ainda são usados na saída da mensagem de `-Confirm`.

```powershell
## $PSCmdlet.ShouldProcess('MESSAGE','TARGET','OPERATION')
What if: MESSAGE
```

### <a name="quick-parameter-reference"></a>Referência de parâmetro rápida

Caso você esteja aqui apenas para descobrir quais parâmetros devem ser usados, aqui está uma referência rápida que mostra como os parâmetros alteram a mensagem nos diferentes cenários de `-WhatIf`.

```powershell
## $PSCmdlet.ShouldProcess('TARGET')
What if: Performing the operation "FUNCTION_NAME" on target "TARGET".

## $PSCmdlet.ShouldProcess('TARGET','OPERATION')
What if: Performing the operation "OPERATION" on target "TARGET".

## $PSCmdlet.ShouldProcess('MESSAGE','TARGET','OPERATION')
What if: MESSAGE
```

Eu costumo usar a opção com dois parâmetros.

### <a name="shouldprocessreason"></a>ShouldProcessReason

Há uma quarta sobrecarga que é mais avançada do que as outras. Ela permite que você entenda o motivo pelo qual `ShouldProcess` foi executado. Estou adicionando isso aqui apenas para fins de integridade, pois é possível apenas verificar se `$WhatIf` é `$true`.

```powershell
$reason = ''
if($PSCmdlet.ShouldProcess('MESSAGE','TARGET','OPERATION',[ref]$reason)){
    Write-Output "Some Action"
}
$reason
```

Precisamos passar a variável `$reason` para o quarto parâmetro como uma variável de referência com `[ref]`. `ShouldProcess` preenche `$reason` com o valor `None` ou `WhatIf`. Eu nunca disse que isso era útil, nem que eu já tenha precisado usar.

### <a name="where-to-place-it"></a>Onde colocar

Você usa `ShouldProcess` para tornar os scripts mais seguros. Portanto, você deve usá-lo quando os scripts estiverem fazendo alterações. Gosto de posicionar a chamada de `$PSCmdlet.ShouldProcess` o mais próximo possível da alteração.

```powershell
## general logic and variable work
if ($PSCmdlet.ShouldProcess('TARGET','OPERATION')){
    # Change goes here
}
```

Se eu estiver processando uma coleção de itens, eu o chamo para cada item. Portanto, a chamada é colocada dentro do loop foreach.

```powershell
foreach ($node in $collection){
    # general logic and variable work
    if ($PSCmdlet.ShouldProcess($node,'OPERATION')){
        # Change goes here
    }
}
```

O motivo pelo qual eu coloco `ShouldProcess` rigidamente ao redor da alteração é porque eu quero que o máximo de códigos possível seja executado quando `-WhatIf` for especificado. Quero que a instalação e a validação sejam executadas, se possível, de maneira que o usuário veja esses erros.

Também gosto de usar isso em testes do Pester que validem meus projetos. Se eu tiver uma parte da lógica difícil de simular em Pester, eu geralmente a encapsulo em `ShouldProcess` e a chamo com `-WhatIf` em meus testes. É melhor testar parte do código do que nenhum código.

### <a name="whatifpreference"></a>$WhatIfPreference

A primeira variável de preferência que temos é `$WhatIfPreference`. Por padrão, é `$false`. Se você a definir como `$true`, a função será executada como se você tivesse especificado `-WhatIf`. Se você definir isso em sua sessão, todos os comandos executarão `-WhatIf`.

Quando você chama uma função com `-WhatIf`, o valor de `$WhatIfPreference` é definido como `$true` dentro do escopo da sua função.

## <a name="confirmimpact"></a>ConfirmImpact

A maioria dos meus exemplos são para `-WhatIf`, mas tudo o que vimos até agora também funciona com `-Confirm` para solicitar ao usuário. Você pode definir a `ConfirmImpact` da função como alta e ela solicitará ao usuário como se fosse chamada com `-Confirm`.

```powershell
function Test-ShouldProcess {
    [CmdletBinding(
        SupportsShouldProcess,
        ConfirmImpact = 'High'
    )]
    param()

    if ($PSCmdlet.ShouldProcess('TARGET')){
        Write-Output "Some Action"
    }
}
```

Essa chamada para `Test-ShouldProcess` está executando a ação `-Confirm` devido ao impacto `High`.

```powershell
PS> Test-ShouldProcess

Confirm
Are you sure you want to perform this action?
Performing the operation "Test-ShouldProcess" on target "TARGET".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y
Some Action
```

O problema óbvio é que agora é mais difícil usar em outros scripts sem avisar o usuário. Nesse caso, podemos passar um `$false` para `-Confirm` para suprimir o prompt.

```powershell
PS> Test-ShouldProcess -Confirm:$false
Some Action
```

Abordarei como adicionar o suporte a `-Force` em uma seção posterior.

### <a name="confirmpreference"></a>$ConfirmPreference

`$ConfirmPreference` é uma variável automática que controla quando `ConfirmImpact` solicita que você confirme a execução. Estes são os valores possíveis tanto para `$ConfirmPreference`, como para `ConfirmImpact`.

- `High`
- `Medium`
- `Low`
- `None`

Com esses valores, você pode especificar diferentes níveis de impacto para cada função. Se você tiver `$ConfirmPreference` definido com um valor maior que `ConfirmImpact`, não será solicitado a confirmar a execução.

Por padrão, `$ConfirmPreference` é definido como `High` e `ConfirmImpact`, como `Medium`. Se você quiser que sua função solicite automaticamente o usuário, defina `ConfirmImpact` como `High`. Caso contrário, defina-o como `Medium` se for destrutivo e use `Low` se o comando for sempre seguro ao executar o ambiente de produção. Se você o definir como `none`, ele não será solicitado mesmo que `-Confirm` tenha sido especificado (mas ainda oferece suporte a `-WhatIf`).

Ao chamar uma função com `-Confirm`, o valor de `$ConfirmPreference` é definido como `Low` dentro do escopo da função.

### <a name="suppressing-nested-confirm-prompts"></a>Como suprimir prompts de confirmação aninhados

O `$ConfirmPreference` pode ser obtido por funções que você chamou. Isso pode criar cenários em que você adiciona um prompt de confirmação e a função que você chama também solicita ao usuário.

Nesse caso, eu geralmente especifico `-Confirm:$false` nos comandos que eu chamo quando já tratei do prompt.

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()

    $file = Get-ChildItem './myfile1.txt'
    if($PSCmdlet.ShouldProcess($file.Name)){
        Remove-Item -Path $file.FullName -Confirm:$false
    }
}
```

Isso nos leva de volta a algo que já alertei antes: Há nuances sobre quando `-WhatIf` não é passado para uma função e quando `-Confirm` passa para uma função. Prometo que tratarei disso depois.

## <a name="pscmdletshouldcontinue"></a>$PSCmdlet.ShouldContinue

Se precisar de mais controle do que `ShouldProcess` fornece, você poderá disparar o prompt diretamente com `ShouldContinue`. `ShouldContinue` ignora `$ConfirmPreference`, `ConfirmImpact`, `-Confirm`, `$WhatIfPreference` e `-WhatIf` porque eles são solicitados toda vez que são executados.

De relance, é fácil confundir `ShouldProcess` e `ShouldContinue`. Eu geralmente me lembro de usar `ShouldProcess` porque o parâmetro é chamado `SupportsShouldProcess` no `CmdletBinding`.
Você deve usar `ShouldProcess` em quase todos os cenários. É por isso que abordei esse método primeiro.

Vamos dar uma olhada no `ShouldContinue` em ação.

```powershell
function Test-ShouldContinue {
    [CmdletBinding()]
    param()

    if($PSCmdlet.ShouldContinue('TARGET','OPERATION')){
        Write-Output "Some Action"
    }
}
```

Isso nos dá um prompt mais simples com menos opções.

```powershell
Test-ShouldContinue

Second
TARGET
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

O maior problema com `ShouldContinue` é que ele requer que o usuário o execute interativamente porque ele sempre solicita ao usuário. Você deve sempre criar ferramentas que podem ser usadas por outros scripts. A maneira de fazer isso é implementar `-Force`. Voltarei a essa ideia mais tarde.

### <a name="yes-to-all"></a>Sim para todos

Isso é manipulado automaticamente com `ShouldProcess`, mas temos que nos esforçar um pouco mais para `ShouldContinue`. Há uma segunda sobrecarga de método em que precisamos passar alguns valores por referência para controlar a lógica.

```powershell
function Test-ShouldContinue {
    [CmdletBinding()]
    param()

    $collection = 1..5
    $yesToAll = $false
    $noToAll = $false

    foreach($target in $collection) {

        $continue = $PSCmdlet.ShouldContinue(
                "TARGET_$target",
                'OPERATION',
                [ref]$yesToAll,
                [ref]$noToAll
            )

        if ($continue){
            Write-Output "Some Action [$target]"
        }
    }
}
```

Adicionei um loop de `foreach` e uma coleção para mostrá-lo em ação. Eu retirei a chamada `ShouldContinue` da instrução `if` para facilitar a leitura. Chamar um método com quatro parâmetros não é muito bonito, mas tentei deixar tudo tão limpo quanto pude.

## <a name="implementing--force"></a>Implementando -Force

`ShouldProcess` e `ShouldContinue` precisam implementar `-Force` de maneiras diferentes. O truque para essas implementações é que `ShouldProcess` sempre deve ser executado, mas `ShouldContinue` não deve ser executado se `-Force` for especificado.

### <a name="shouldprocess--force"></a>ShouldProcess -Force

Se você definir `ConfirmImpact` como `high`, a primeira coisa que os usuários tentarão é suprimi-lo com `-Force`. Essa é a primeira coisa que eu faço, pelo menos.

```powershell
Test-ShouldProcess -Force
Error: Test-ShouldProcess: A parameter cannot be found that matches parameter name 'force'.
```

Se você se lembra da seção `ConfirmImpact`, eles precisam chamá-la da seguinte maneira:

```powershell
Test-ShouldProcess -Confirm:$false
```

Nem todos percebem que eles precisam fazer isso e que `-Confirm:$false` não suprime `ShouldContinue`.
Então, devemos implementar `-Force` pelo bem da saúde mental de nossos usuários. Dê uma olhada neste exemplo completo:

```powershell
function Test-ShouldProcess {
    [CmdletBinding(
        SupportsShouldProcess,
        ConfirmImpact = 'High'
    )]
    param(
        [Switch]$Force
    )

    if ($Force -and -not $Confirm){
        $ConfirmPreference = 'None'
    }

    if ($PSCmdlet.ShouldProcess('TARGET')){
        Write-Output "Some Action"
    }
}
```

Adicionamos nossa própria opção de `-Force` como um parâmetro e usamos o parâmetro automático `$Confirm` que está disponível ao adicionar `SupportsShouldProcess` no `CmdletBinding`.

```powershell
[CmdletBinding(
    SupportsShouldProcess,
    ConfirmImpact = 'High'
)]
param(
    [Switch]$Force
)
```

Concentrando-se na lógica de `-Force` aqui:

```powershell
if ($Force -and -not $Confirm){
    $ConfirmPreference = 'None'
}
```

Se o usuário especificar `-Force`, precisaremos suprimir a solicitação de confirmação, a não ser que também especifique `-Confirm`. Isso permite que um usuário force uma alteração, mas ainda confirma a alteração. Em seguida, definimos `$ConfirmPreference` no escopo local onde nossa chamada para `ShouldProcess` os descobre.

```powershell
if ($PSCmdlet.ShouldProcess('TARGET')){
        Write-Output "Some Action"
    }
```

Caso alguém especifique `-Force` e `-WhatIf`, então `-WhatIf` precisará ter prioridade. Essa abordagem preserva o processamento de `-WhatIf` porque `ShouldProcess` sempre é executado.

Não adicione uma verificação para o valor de `$Force` dentro da instrução `if` com o `ShouldProcess`. Esse é um antipadrão para esse cenário específico, embora seja a mesma coisa que eu mostrarei na próxima seção para `ShouldContinue`.

### <a name="shouldcontinue--force"></a>ShouldContinue-Force

Essa é a maneira correta de implementar `-Force` com `ShouldContinue`.

```powershell
function Test-ShouldContinue {
    [CmdletBinding()]
    param(
        [Switch]$Force
    )

    if($Force -or $PSCmdlet.ShouldContinue('TARGET','OPERATION')){
        Write-Output "Some Action"
    }
}
```

Ao colocar o `$Force` à esquerda do operador de `-or`, ele é avaliado primeiro. Escrevê-lo dessa forma causa o curto-circuito da execução da instrução `if`. Se `$force` for `$true`, o `ShouldContinue` não será executado.

```powershell
PS> Test-ShouldContinue -Force
Some Action
```

Não precisamos nos preocupar com `-Confirm` ou `-WhatIf` nesse cenário porque eles não têm suporte do `ShouldContinue`. É por isso que precisamos tratá-lo de maneira diferente do `ShouldProcess`.

## <a name="scope-issues"></a>Problemas de escopo

`-WhatIf` e `-Confirm` devem ser aplicados a tudo dentro de funções e a tudo que eles chamam. Eles o fazem definindo `$WhatIfPreference` como `$true` ou definindo `$ConfirmPreference` como `Low` no escopo local da função. Quando você chama outra função, as chamadas para `ShouldProcess` usam esses valores.

Isso funciona na maioria das vezes. Sempre que você chamar o cmdlet interno ou uma função no mesmo escopo, isso funcionará. Também funcionará quando você chamar um script ou uma função em um módulo de script do console.

O local específico em que ele não funciona é quando um script ou um módulo de script chama uma função em outro módulo de script. Isso pode não parecer um grande problema, mas a maioria dos módulos criados ou extraídos do PSGallery são módulos de script.

O principal problema é que os módulos de script não herdam os valores de `$WhatIfPreference` ou `$ConfirmPreference` (e várias outros) quando chamados de funções em outros módulos de script.

A melhor maneira de resumir isso em uma regra geral é que funciona corretamente para módulos binários, mas não é confiável para módulos de script. Caso você não tenha certeza, teste-o ou apenas presuma que ele não funciona corretamente.

Pessoalmente, eu acredito que isso é muito perigoso, pois cria cenários em que você adiciona suporte para `-WhatIf` a vários módulos que funcionam corretamente em isolamento, mas não quando chamam um ao outro.

Há uma RFC do GitHub trabalhando para corrigir esse problema. Consulte [Propagar as preferências de execução além do escopo do módulo de script][RFC] para obter mais detalhes.

## <a name="in-closing"></a>Concluindo

Tenho que pesquisar como usar `ShouldProcess` toda vez que preciso usá-lo. Demorei muito tempo para conseguir distinguir `ShouldProcess` de `ShouldContinue`. Eu quase sempre preciso pesquisar os parâmetros para usá-los. Então, não se preocupe se você ainda se sentir confuso de vez em quando. Este artigo estará aqui sempre que você precisar. Tenho certeza de que eu mesmo vou consultá-lo com frequência.

Se você gostou desta postagem, compartilhe seus pensamentos comigo no Twitter usando o link abaixo. Gosto de saber das pessoas que apreciam meus conteúdos.

<!-- link references -->
[versão original]: https://powershellexplained.com/2020-03-15-Powershell-shouldprocess-whatif-confirm-shouldcontinue-everything/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[parâmetros comuns]: /powershell/module/microsoft.powershell.core/about/about_commonparameters
[Tudo o que você queria saber sobre as tabelas de hash]: everything-about-hashtable.md
[RFC]: https://github.com/PowerShell/PowerShell-RFC/pull/221#issuecomment-592954839
