---
ms.date: 09/14/2020
title: Usar recursos experimentais no PowerShell
description: Lista os recursos experimentais disponíveis no momento e como usá-los.
ms.openlocfilehash: 74623240bfb19022ae342a5d23e2ed4f455afa45
ms.sourcegitcommit: 30c0c1563f8e840f24b65297e907f3583d90e677
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90574463"
---
# <a name="using-experimental-features-in-powershell"></a>Usar recursos experimentais no PowerShell

O suporte de recursos experimentais no PowerShell fornece um mecanismo para que os recursos experimentais coexistam com os recursos estáveis existentes nos módulos PowerShell ou PowerShell.

Um recurso experimental é aquele em que o design não está finalizado. O recurso está disponível para os usuários testarem e fornecerem comentários. Depois que um recurso experimental é finalizado, as alterações de design se tornam alterações interruptivas.

> [!CAUTION]
> Os recursos experimentais não devem ser usados na produção, já que as alterações podem causar problemas. Recursos experimentais não têm suporte oficialmente. No entanto, agradecemos o envio de comentários e relatórios de bugs. Você pode arquivar problemas no [repositório de origem do GitHub](https://github.com/PowerShell/PowerShell/issues/new/choose).

Para obter mais informações sobre como habilitar ou desabilitar esses recursos, confira [about_Experimental_Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features).

## <a name="available-features"></a>Recursos disponíveis

Este artigo descreve os recursos experimentais que estão disponíveis e como usar o recurso.

|                            Nome                            |   6.2   |   7.0   |   7.1   |
| ---------------------------------------------------------- | :-----: | :-----: | :-----: |
| PSTempDrive (base no PS 7.0+)                        | &check; |         |         |
| PSUseAbbreviationExpansion (base no PS 7.0+)         | &check; |         |         |
| PSCommandNotFoundSuggestion                                | &check; | &check; | &check; |
| PSImplicitRemotingBatching                                 | &check; | &check; | &check; |
| Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace |         | &check; | &check; |
| PSDesiredStateConfiguration.InvokeDscResource              |         | &check; | &check; |
| PSNullConditionalOperators (base no PS 7.1+)         |         | &check; |         |
| PSUnixFileStat (somente não Windows)                          |         | &check; | &check; |
| PSNativePSPathResolution (base no PS 7.1+)           |         |         |         |
| PSCultureInvariantReplaceOperator                          |         |         | &check; |
| PSNotApplyErrorActionToStderr                              |         |         | &check; |

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

> [!NOTE]
> Esse recurso foi removido da fase experimental e é um recurso base do PowerShell 7.1 e posterior.

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

## <a name="psuseabbreviationexpansion"></a>PSUseAbbreviationExpansion

Esse recurso permite o preenchimento com Tab de funções e cmdlets abreviados:

Por exemplo: 

- `i-psdf<tab>` retorna `Import-PowerShellDataFile`.
- `u-akvmssdr<tab>` retorna `Undo-AzKeyVaultManagedStorageSasDefinitionRemoval`

Isso só funciona para preenchimento com Tab (uso interativo), portanto, `i-psdf` não é um nome de cmdlet válido em um script.

> [!NOTE]
> Esse recurso foi removido da fase experimental e é um recurso base do PowerShell 7 e superior.
