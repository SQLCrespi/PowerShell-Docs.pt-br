---
description: Descreve os pipelines de encadeamento com `&&` os `||` operadores e no PowerShell.
Locale: en-US
ms.date: 09/30/2019
schema: 2.0.0
title: about_Pipeline_Chain_Operators
ms.openlocfilehash: ece84ec061126401e53bf58112cd79a07a816e8d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598655"
---
# <a name="about-pipeline-chain-operators"></a>Sobre operadores de cadeia de pipeline

## <a name="short-description"></a>Descrição breve

Descreve os pipelines de encadeamento com `&&` os `||` operadores e no PowerShell.

## <a name="long-description"></a>Descrição longa

A partir do PowerShell 7, o PowerShell implementa os `&&` `||` operadores e para encadear pipelines condicionalmente. Esses operadores são conhecidos no PowerShell como *operadores de cadeia de pipeline* e são semelhantes às [listas e-ou](https://pubs.opengroup.org/onlinepubs/009695399/utilities/xcu_chap02.html#tag_02_09_03) em shells POSIX, como bash, zsh e sh, bem como [símbolos de processamento condicional](/previous-versions/windows/it-pro/windows-xp/bb490954(v=technet.10)#using-multiple-commands-and-conditional-processing-symbols) no Shell de comando do Windows (cmd.exe).

O operador `&&` executa o pipeline à direita, se o pipeline à esquerda foi bem-sucedido. Por outro lado, o operador `||` executa o pipeline à direita, se o pipeline à esquerda falhou.

Esses operadores usam as variáveis `$?` e `$LASTEXITCODE` para determinar se um pipeline falhou. Isso permite que você os utilize com comandos nativos, e não apenas com cmdlets ou funções. Por exemplo:

```powershell
# Create an SSH key pair - if successful copy the public key to clipboard
ssh-keygen -t rsa -b 2048 && Get-Content -Raw ~\.ssh\id_rsa.pub | clip
```

### <a name="examples"></a>Exemplos

#### <a name="two-successful-commands"></a>Dois comandos bem-sucedidos

```powershell
Write-Output 'First' && Write-Output 'Second'
```

```Output
First
Second
```

#### <a name="first-command-fails-causing-second-not-to-be-executed"></a>O primeiro comando falha, fazendo com que o segundo não seja executado

```powershell
Write-Error 'Bad' && Write-Output 'Second'
```

```Output
Write-Error: Bad
```

#### <a name="first-command-succeeds-so-the-second-command-is-not-executed"></a>O primeiro comando é bem sucedido; portanto, o segundo comando não é executado

```powershell
Write-Output 'First' || Write-Output 'Second'
```

```Output
First
```

#### <a name="first-command-fails-so-the-second-command-is-executed"></a>O primeiro comando falha, portanto, o segundo comando é executado

```powershell
Write-Error 'Bad' || Write-Output 'Second'
```

```Output
Write-Error: Bad
Second
```

O êxito do pipeline é definido pelo valor da `$?` variável, que o PowerShell define automaticamente após a execução de um pipeline com base em seu status de execução.
Isso significa que os operadores de cadeia de pipeline têm a seguinte equivalência:

```powershell
Test-Command '1' && Test-Command '2'
```

funciona da mesma forma que

```powershell
Test-Command '1'; if ($?) { Test-Command '2' }
```

e

```powershell
Test-Command '1' || Test-Command '2'
```

funciona da mesma forma que

```powershell
Test-Command '1'; if (-not $?) { Test-Command '2' }
```

### <a name="assignment-from-pipeline-chains"></a>Atribuição de cadeias de pipeline

A atribuição de uma variável de uma cadeia de pipeline usa a concatenação de todos os pipelines na cadeia:

```powershell
$result = Write-Output '1' && Write-Output '2'
$result
```

```Output
1
2
```

Se ocorrer um erro de encerramento de script durante a atribuição de uma cadeia de pipeline, a atribuição não terá sucesso:

```powershell
try
{
    $result = Write-Output 'Value' && $(throw 'Bad')
}
catch
{
    # Do nothing, just squash the error
}

"Result: $result"
```

```Output
Result:
```

### <a name="operator-syntax-and-precedence"></a>Sintaxe e precedência do operador

Ao contrário de outros operadores, `&&` e `||` operam em pipelines, em vez de expressões como `+` ou `-and` , por exemplo.

`&&` e `||` têm uma precedência mais baixa do que o de tubulação () `|` ou redirecionamento ( `>` ), mas uma precedência mais alta do que os operadores de trabalho ( `&` ), atribuição ( `=` ) ou ponto-e-vírgula ( `;` ). Isso significa que os pipelines em uma cadeia de pipeline podem ser redirecionados individualmente e que todas as cadeias de pipeline podem ser em segundo plano, atribuídas a variáveis ou separadas como instruções.

Para usar a sintaxe de precedência inferior em uma cadeia de pipeline, considere o uso de parênteses `(...)` .
Da mesma forma, para inserir uma instrução em uma cadeia de pipeline, uma subexpressão `$(...)` pode ser usada.
Isso pode ser útil para combinar comandos nativos com o fluxo de controle:

```powershell
foreach ($file in 'file1','file2','file3')
{
    # When find succeeds, the loop breaks
    find $file && Write-Output "Found $file" && $(break)
}
```

```Output
find: file1: No such file or directory
file2
Found file2
```

A partir do PowerShell 7, o comportamento dessas sintaxes foi alterado para que `$?` seja definido como esperado quando um comando é executado com êxito ou falha entre parênteses ou uma subexpressão.

Como a maioria dos outros operadores no PowerShell `&&` e `||` também são *associativas à esquerda*, o que significa que eles são agrupados da esquerda. Por exemplo:

```powershell
Get-ChildItem -Path ./file.txt || Write-Error "file.txt does not exist" && Get-Content -Raw ./file.txt
```

será agrupado como:

```
[Get-ChildItem -Path ./file.txt || Write-Error "file.txt does not exist"] && Get-Content -Raw ./file.txt
```

sendo equivalente a:

```powershell
Get-ChildItem -Path ./file.txt

if (-not $?) { Write-Error "file.txt does not exist" }

if ($?) { Get-Content -Raw ./file.txt }
```

### <a name="error-interaction"></a>Interação de erro

Os operadores de cadeia de pipeline não absorvem erros. Quando uma instrução em uma cadeia de pipeline gera um erro de encerramento de script, a cadeia de pipeline é encerrada.

Por exemplo:

```powershell
$(throw 'Bad') || Write-Output '2'
```

```Output
Exception: Bad
```

Mesmo quando o erro é capturado, a cadeia de pipeline ainda é encerrada:

```powershell
try
{
    $(throw 'Bad') || Write-Output '2'
}
catch
{
    Write-Output "Caught: $_"
}
Write-Output 'Done'
```

```Output
Caught: Bad
Done
```

Se um erro não estiver sendo encerrado ou apenas terminar um pipeline, a cadeia de pipeline continuará, respeitando o valor de `$?` :

```powershell
function Test-NonTerminatingError
{
    [CmdletBinding()]
    param()

    $exception = [System.Exception]::new('BAD')
    $errorId = 'BAD'
    $errorCategory = 'NotSpecified'

    $errorRecord = [System.Management.Automation.ErrorRecord]::new($exception, $errorId, $errorCategory, $null)

    $PSCmdlet.WriteError($errorRecord)
}

Test-NonTerminatingError || Write-Output 'Second'
```

```Output
Test-NonTerminatingError: BAD
Second
```

### <a name="chaining-pipelines-rather-than-commands"></a>Encadeando pipelines em vez de comandos

Os operadores de cadeia de pipeline, por seu nome, podem ser usados para encadear pipelines, em vez de apenas comandos. Isso corresponde ao comportamento de outros shells, mas pode dificultar o *sucesso* de determinar:

```powershell
function Test-NotTwo
{
    [CmdletBinding()]
    param(
      [Parameter(ValueFromPipeline)]
      $Input
    )

    process
    {
        if ($Input -ne 2)
        {
            return $Input
        }

        $exception = [System.Exception]::new('Input is 2')
        $errorId = 'InputTwo'
        $errorCategory = 'InvalidData'

        $errorRecord = [System.Management.Automation.ErrorRecord]::new($exception, $errorId, $errorCategory, $null)

        $PSCmdlet.WriteError($errorRecord)
    }
}

1,2,3 | Test-NotTwo && Write-Output 'All done!'
```

```Output
1
Test-NotTwo : Input is 2
3
```

Observe que `Write-Output 'All done!'` não é executado, uma vez que `Test-NotTwo` é considerado com falha após gerar o erro de não finalização.

## <a name="see-also"></a>Consulte também

- [about_Operators](about_Operators.md)
- [about_Automatic_Variables](about_Automatic_Variables.md)
- [about_pipelines](about_pipelines.md)

