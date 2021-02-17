---
ms.date: 12/14/2020
title: Usar recursos experimentais no PowerShell
description: Lista os recursos experimentais disponíveis no momento e como usá-los.
ms.openlocfilehash: 556ae8d877b670b119b7b5b958a52488aad16241
ms.sourcegitcommit: 77f6225ab0c8ea9faa1fe46b2ea15c178ec170e3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100500116"
---
# <a name="using-experimental-features-in-powershell"></a>Usar recursos experimentais no PowerShell

O suporte de recursos experimentais no PowerShell fornece um mecanismo para que os recursos experimentais coexistam com os recursos estáveis existentes nos módulos PowerShell ou PowerShell.

Um recurso experimental é aquele em que o design não está finalizado. O recurso está disponível para os usuários testarem e fornecerem comentários. Depois que um recurso experimental é finalizado, as alterações de design se tornam alterações interruptivas.

> [!CAUTION]
> Os recursos experimentais não devem ser usados na produção, já que as alterações podem causar problemas. Recursos experimentais não têm suporte oficialmente. No entanto, agradecemos o envio de comentários e relatórios de bugs. Você pode arquivar problemas no [repositório de origem do GitHub](https://github.com/PowerShell/PowerShell/issues/new/choose).

Para obter mais informações sobre como habilitar ou desabilitar esses recursos, confira [about_Experimental_Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features).

## <a name="available-features"></a>Recursos disponíveis

Este artigo descreve os recursos experimentais que estão disponíveis e como usar o recurso.

|                            Nome                            |   6.2   |   7.0   |   7.1   |   7.2   |
| ---------------------------------------------------------- | :-----: | :-----: | :-----: | :-----: |
| PSTempDrive (base no PS 7.0+)                        | &check; |         |         |         |
| PSUseAbbreviationExpansion (base no PS 7.0+)         | &check; |         |         |         |
| PSNullConditionalOperators (base no PS 7.1+)         |         | &check; |         |         |
| PSUnixFileStat (somente não Windows – base no PS 7.1+)  |         | &check; |         |         |
| PSCommandNotFoundSuggestion                                | &check; | &check; | &check; | &check; |
| PSImplicitRemotingBatching                                 | &check; | &check; | &check; | &check; |
| Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace |         | &check; | &check; | &check; |
| PSDesiredStateConfiguration.InvokeDscResource              |         | &check; | &check; | &check; |
| PSNativePSPathResolution                                   |         |         | &check; | &check; |
| PSCultureInvariantReplaceOperator                          |         |         | &check; | &check; |
| PSNotApplyErrorActionToStderr                              |         |         | &check; | &check; |
| PSSubsystemPluginModel                                     |         |         | &check; | &check; |
| PSAnsiProgress                                             |         |         |         | &check; |
| PSAnsiRendering                                            |         |         |         | &check; |

## <a name="microsoftpowershellutilitypsmanagebreakpointsinrunspace"></a>Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace

No PowerShell 7.0, o experimento habilita o parâmetro **BreakAll** nos cmdlets `Debug-Runspace` e `Debug-Job` para permitir que os usuários decidam se querem que o PowerShell seja interrompido imediatamente no local atual quando eles anexarem um depurador.

No PowerShell 7.1, esse experimento também adiciona o parâmetro **Runspace** aos cmdlets `*-PSBreakpoint`.

- `Disable-PSBreakpoint`
- `Enable-PSBreakpoint`
- `Get-PSBreakpoint`
- `Remove-PSBreakpoint`
- `Set-PSBreakpoint`

O parâmetro **Runspace** especifica um objeto **Runspace** para interagir com pontos de interrupção no runspace especificado.

```powershell
Start-Job -ScriptBlock {
    Set-PSBreakpoint -Command Start-Sleep
    Start-Sleep -Seconds 10
}

$runspace = Get-Runspace -Id 1

$breakpoint = Get-PSBreakPoint -Runspace $runspace
```

Nesse exemplo, um trabalho é iniciado e um ponto de interrupção é definido para interromper quando `Set-PSBreakPoint` for executado. O runspace é armazenado em uma variável e transmitido para o comando `Get-PSBreakPoint` com o parâmetro **Runspace**. Em seguida, você pode inspecionar o ponto de interrupção na variável `$breakpoint`.

## <a name="psansirendering"></a>PSAnsiRendering

O experimento foi adicionado no PowerShell 7.2. O recurso permite alterar a forma como o mecanismo do PowerShell gera texto e adiciona a variável automática `$PSStyle` para controlar a renderização ANSI da saída da cadeia de caracteres.

```powershell
PS> $PSStyle

Name            MemberType Definition
----            ---------- ----------
Reset           Property   string AttributesOff {get;set;}
Background      Property   System.Management.Automation.PSStyle+BackgroundColor Background {get;set;}
Blink           Property   string Blink {get;set;}
BlinkOff        Property   string BlinkOff {get;set;}
Bold            Property   string Bold {get;set;}
BoldOff         Property   string BoldOff {get;set;}
Foreground      Property   System.Management.Automation.PSStyle+ForegroundColor Foreground {get;set;}
Formatting      Property   System.Management.Automation.PSStyle+FormattingData Formatting {get;set;}
Hidden          Property   string Hidden {get;set;}
HiddenOff       Property   string HiddenOff {get;set;}
OutputRendering Property   System.Management.Automation.OutputRendering OutputRendering {get;set;}
Reverse         Property   string Reverse {get;set;}
ReverseOff      Property   string ReverseOff {get;set;}
Italic          Property   string Standout {get;set;}
ItalicOff       Property   string StandoutOff {get;set;}
Underline       Property   string Underlined {get;set;}
Underline Off   Property   string UnderlinedOff {get;set;}
```

Os membros de base retornam cadeias de caracteres de sequências de escape ANSI mapeadas para seus nomes. Os valores são configuráveis para permitir a personalização.

Para obter mais informações, confira [about_Automatic_Variables](/reference/7.2/Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

> [!NOTE]
> Para desenvolvedores C#, você pode acessar `PSStyle` como um singleton. O uso terá esta aparência:
>
> ```csharp
> string output = $"{PSStyle.Instance.Foreground.Red}{PSStyle.Instance.Bold}Hello{PSStyle.Instance.Reset}";
> ```
>
> `PSStyle` existe no namespace System.Management.Automation.

Junto com o acesso ao `$PSStyle`, isso apresenta alterações no mecanismo do PowerShell. O sistema de formatação do PowerShell é atualizado para respeitar `$PSStyle.OutputRendering`.

- O tipo `StringDecorated` é adicionado para manipular cadeias de caracteres de escape ANSI.
- A propriedade booliana `string IsDecorated` é adicionada para retornar se a cadeia de caracteres contém sequências de escape ANSI com base em se a cadeia de caracteres contém ESC ou C1 CSI.
- A propriedade `Length` retorna _apenas_ o comprimento do texto sem as sequências de escape ANSI.
- O método `StringDecorated Substring(int contentLength)` retorna uma substring começando no índice 0 até o comprimento do conteúdo que não faz parte das sequências de escape ANSI. Isso é necessário para a formatação da tabela a fim de truncar cadeias de caracteres e preservar as sequências de escape ANSI que não ocupam espaço de caracteres imprimível.
- O método `string ToString()` permanece o mesmo e retorna a versão de texto não criptografado da cadeia de caracteres.
- O método `string ToString(bool Ansi)` retornará a cadeia de caracteres ANSI bruta inserida se o parâmetro `Ansi` for true. Caso contrário, uma versão de texto não criptografado com sequências de escape ANSI removidas será retornada.

## <a name="psansiprogress"></a>PSAnsiProgress

O experimento foi adicionado no PowerShell 7.2. O recurso adiciona o membro `$PSStyle.Progress` e permite controlar a renderização da barra de exibição de progresso.

- `$PSStyle.Progress.Style` – uma cadeia de caracteres ANSI que define o estilo de renderização.
- `$PSStyle.Progress.MaxWidth` – define a largura máxima da exibição. Defina como `0` para a largura do console.
  Usa como padrão `120`
- `$PSStyle.Progress.View` – uma enumeração com valores `Minimal` e `Classic`. `Classic` é a renderização existente sem alterações. `Minimal` é uma renderização mínima de linha única. `Minimal` é o padrão.

O exemplo a seguir atualiza o estilo de renderização para uma barra de progresso mínima.

```powershell
$PSStyle.Progress.View.Minimal
```

> [!NOTE]
> O recurso experimental **PSAnsiRendering** deve estar habilitado para usar esse recurso.

## <a name="pscommandnotfoundsuggestion"></a>PSCommandNotFoundSuggestion

Recomenda comandos potenciais com base na pesquisa de correspondência difusa após um **CommandNotFoundException**.

```powershell
PS> get
```

```Output
get: The term 'get' is not recognized as the name of a cmdlet, function, script file, or operable
program. Check the spelling of the name, or if a path was included, verify that the path is correct
and try again.

Suggestion [4,General]: The most similar commands are: set, del, ft, gal, gbp, gc, gci, gcm, gdr,
gcs.
```

## <a name="pscultureinvariantreplaceoperator"></a>PSCultureInvariantReplaceOperator

Quando o operando à esquerda em uma instrução do operador `-replace` não é uma cadeia de caracteres, esse operando é convertido em uma cadeia de caracteres.

Quando esse recurso está desabilitado, o operador `-replace` faz uma conversão de cadeia de caracteres sensível à cultura.
Por exemplo, se sua cultura for definida como francês (FR), o valor `1.2` será convertido para a cadeia de caracteres `1,2`.

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr'
PS> 1.2 -replace ','
12
PS> [cultureinfo]::CurrentCulture = 'en'
PS> 1.2 -replace ','
1.2
```

Com o recurso habilitado:

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr'
PS> 1.2 -replace ','
1.2
```

## <a name="psdesiredstateconfigurationinvokedscresource"></a>PSDesiredStateConfiguration.InvokeDscResource

Habilita a compilação para o formato MOF em sistemas que não são do Windows e permite o uso de `Invoke-DSCResource` sem um LCM.

## <a name="psimplicitremotingbatching"></a>PSImplicitRemotingBatching

Esse recurso examina o comando digitado no shell e, se todos os comandos forem comandos de proxy de comunicação remota implícitos que formam um pipeline simples, os comandos serão agrupados em lote e invocados como um único pipeline remoto.

Exemplo:

```powershell
# Create remote session and import TestIMod module
$s = nsn -host remoteMachine
icm $s { ipmo 'C:\Users\user\Documents\WindowsPowerShell\Modules\TestIMod\TestIMod.psd1' }
Import-PSSession $s -mod testimod

$maxProcs = 1000
$filter = 'pwsh','powershell*','wmi*'

# Without batching, this pipeline takes approximately 12 seconds to run
Measure-Command { Get-AllProcesses -MaxCount $maxProcs | Select-Custom $filter | Group-Stuff $filter }
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 12
Milliseconds      : 463

# But with the batching experimental feature enabled, it takes approximately 0.20 seconds
Measure-Command { Get-AllProcesses -MaxCount $maxProcs | Select-Custom $filter | Group-Stuff $filter }
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 0
Milliseconds      : 209
```

Como visto acima, com o recurso de envio em lote habilitado, todos os três comandos de proxy de comunicação remota implícito, `Get-AllProcesses`, `Select-Custom`, `Group-Stuff`, executados na sessão remota e o resultado do pipeline são os únicos dados retornados ao cliente. Isso diminui a quantidade de dados enviados entre o cliente e a sessão remota, além de reduzir a quantidade de serialização e desserialização de objetos.

## <a name="psnativepspathresolution"></a>PSNativePSPathResolution

Se um caminho PSDrive que usa o provedor FileSystem for passado para um comando nativo, o caminho do arquivo resolvido será passado para o comando nativo. Isso significa que um comando como `code temp:/test.txt` agora funciona conforme o esperado.

Além disso, no Windows, se o caminho começar com `~`, isso será resolvido para o caminho completo e passado para o comando nativo. Em ambos os casos, o caminho é normalizado para os separadores de diretório para o sistema operacional relevante.

- Se o caminho não for um PSDrive ou `~` (no Windows), a normalização de caminho não ocorrerá
- Se o caminho estiver entre aspas simples, ele não será resolvido e tratado como literal

## <a name="psnotapplyerroractiontostderr"></a>PSNotApplyErrorActionToStderr

Quando esse recurso experimental está habilitado, os registros de erro redirecionados de comandos nativos, como ao usar operadores de redirecionamento (`2>&1`), não são gravados na variável `$Error`, e a variável de preferência `$ErrorActionPreference` não afeta a saída redirecionada.

Muitos comandos nativos gravam em `stderr` como um fluxo alternativo para obter informações adicionais. Esse comportamento pode causar confusão ao examinar erros, ou o usuário pode perder as informações de saída adicionais caso `$ErrorActionPreference` esteja definido como um estado que desativa a saída.

Quando um comando nativo tem um código de saída diferente de zero, `$?` é definido como `$false`. Se o código de saída for zero, `$?` será definido como `$true`.

## <a name="psnullconditionaloperators"></a>PSNullConditionalOperators

Apresenta novos operadores para operadores de acesso a membros condicional nulo – `?.` e `?[]`. Operadores de acesso a membros nulo podem ser usados em tipos escalares e tipos de matriz. Retorne o valor do membro acessado se a variável não for nula. Se o valor da variável for nulo, retornará nulo.

```powershell
$x = $null
${x}?.propname
${x?}?.propname

${x}?[0]
${x?}?[0]

${x}?.MyMethod()
```

A propriedade `propname` é acessada, e seu valor será retornado somente se `$x` não for nulo. Da mesma forma, o indexador será usado somente se `$x` não for nulo. Se `$x` for nulo, nulo será retornado.

Os operadores `?.` e `?[]` são operadores de acesso a membros e não permitem um espaço entre o nome da variável e o operador.

Como o PowerShell permite `?` como parte do nome da variável, a desambiguidade é necessária quando os operadores são usados sem um espaço entre o nome da variável e o operador. Para desambiguar, as variáveis devem usar `{}` em volta do nome da variável, como: `${x?}?.propertyName` ou `${y}?[0]`.

> [!NOTE]
> Esse recurso foi removido da fase experimental e é um recurso base do PowerShell 7.1 e posterior.

## <a name="pstempdrive"></a>PSTempDrive

Cria o PSDrive `TEMP:` mapeado para o caminho do diretório temporário do usuário.

> [!NOTE]
> Esse recurso foi removido da fase experimental e é um recurso base do PowerShell 7 e superior.

## <a name="psunixfilestat"></a>PSUnixFileStat

Esse recurso fornece um novo comportamento para incluir dados da API **stat** do UNIX na saída do provedor do sistema de arquivos para facilitar uma listagem de arquivos semelhante ao UNIX. Ele adiciona uma nova propriedade de anotação no provedor filesystem chamado **UnixStat** que inclui uma expressão comum da API `stat(2)` do sistema de tipos UNIX subjacente.

A saída de `Get-ChildItem` deve ser semelhante a esta:

```powershell
dir | select -first 4 -skip 5


    Directory: /Users/jimtru/src/github/forks/JamesWTruher/PowerShell-1

UnixMode   User      Group           LastWriteTime        Size Name
--------   ----      -----           -------------        ---- ----
drwxr-xr-x jimtru    staff        10/23/2019 13:16         416 test
drwxr-xr-x jimtru    staff         11/8/2019 10:37         896 tools
-rw-r--r-- jimtru    staff         11/8/2019 10:37      112858 build.psm1
-rw-r--r-- jimtru    staff         11/8/2019 10:37      201297 CHANGELOG.md
```

> [!NOTE]
> Esse recurso foi removido da fase experimental e é um recurso base do PowerShell 7.1 e posterior.

## <a name="psuseabbreviationexpansion"></a>PSUseAbbreviationExpansion

Esse recurso permite o preenchimento com Tab de funções e cmdlets abreviados:

Por exemplo: 

- `i-psdf<tab>` retorna `Import-PowerShellDataFile`.
- `u-akvmssdr<tab>` retorna `Undo-AzKeyVaultManagedStorageSasDefinitionRemoval`

Isso só funciona para preenchimento com Tab (uso interativo), portanto, `i-psdf` não é um nome de cmdlet válido em um script.

> [!NOTE]
> Esse recurso foi removido da fase experimental e é um recurso base do PowerShell 7 e superior.

## <a name="pssubsystempluginmodel"></a>PSSubsystemPluginModel

Esse recurso habilita o modelo de plug-in do subsistema no PowerShell. Ele possibilita a separação dos componentes de `System.Management.Automation.dll` em subsistemas individuais que residem no próprio assembly. Essa divisão reduz o volume de disco do mecanismo principal do PowerShell e permite que esses componentes se tornem recursos opcionais para uma instalação mínima do PowerShell.

Atualmente, há suporte apenas para o subsistema **CommandPredictor**. Esse subsistema é usado com o módulo PSReadLine para fornecer plug-ins de previsão personalizados. No futuro, será possível dividir **Job**, **CommandCompleter**, **Remoting** e outros componentes em assemblies de subsistema fora do `System.Management.Automation.dll`.

O recurso experimental inclui um novo cmdlet, o [Get-PSSubsystem](xref:Microsoft.PowerShell.Core.Get-PSSubsystem). Esse cmdlet só está disponível quando o recurso está habilitado. Esse cmdlet retorna informações sobre os subsistemas disponíveis no sistema.
