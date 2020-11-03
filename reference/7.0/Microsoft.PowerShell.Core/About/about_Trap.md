---
description: Descreve uma palavra-chave que manipula um erro de encerramento.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_trap?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Trap
ms.openlocfilehash: 1e5541ce45e4dea8ebe87aa76a984f7d3de8c51f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195464"
---
# <a name="about-trap"></a>Sobre interceptação

## <a name="short-description"></a>Descrição breve

Descreve uma palavra-chave que manipula um erro de encerramento.

## <a name="long-description"></a>Descrição longa

Um erro de encerramento interrompe a execução de uma instrução. Se o PowerShell não tratar um erro de encerramento de alguma forma, o PowerShell também interromperá a execução da função ou do script no pipeline atual. Em outras linguagens, como C#, os erros de encerramento são conhecidos como exceções.

A `trap` palavra-chave especifica uma lista de instruções a serem executadas quando ocorre um erro de encerramento. `trap` as instruções manipulam os erros de encerramento das seguintes maneiras:

- Exiba o erro depois de processar o `trap` bloco de instrução e continuar a execução do script ou da função que contém o `trap` . Esse é o comportamento padrão.

- Exiba o erro e anule a execução do script ou da função que contém o `trap` usando `break` na `trap` instrução.

- Silenciar o erro, mas continuar a execução do script ou da função que contém o usando `trap` `continue` na `trap` instrução.

A lista de instruções do `trap` pode incluir várias condições ou chamadas de função. Um `trap` pode gravar logs, condições de teste ou até mesmo executar outro programa.

### <a name="syntax"></a>Syntax

A `trap` instrução tem a seguinte sintaxe:

```powershell
trap [[<error type>]] {<statement list>}
```

A `trap` instrução inclui uma lista de instruções a serem executadas quando ocorre um erro de encerramento. Uma `trap` instrução consiste na `trap` palavra-chave, opcionalmente seguida por uma expressão de tipo, e o bloco de instrução que contém a lista de instruções a serem executadas quando um erro é interceptado. A expressão de tipo restringe os tipos de erros que o `trap` captura.

Um script ou comando pode ter várias `trap` instruções. `trap` as instruções podem aparecer em qualquer lugar no script ou comando.

### <a name="trapping-all-terminating-errors"></a>Interceptando todos os erros de encerramento

Quando ocorre um erro de encerramento que não é tratado de outra maneira em um script ou comando, o PowerShell verifica uma `trap` instrução que manipula o erro. Se uma `trap` instrução estiver presente, o PowerShell continuará executando o script ou o comando na `trap` instrução.

O exemplo a seguir é uma instrução muito simples `trap` :

```powershell
trap {"Error found."}
```

Essa `trap` instrução intercepta qualquer erro de encerramento.

No exemplo a seguir, a função inclui uma cadeia de caracteres de sentido que causa um erro de tempo de execução.

```powershell
function TrapTest {
    trap {"Error found."}
    nonsenseString
}

TrapTest
```

A execução dessa função retorna o seguinte:

```Output
Error found.
nonsenseString:
Line |
   3 |      nonsenseString
     |      ~~~~~~~~~~~~~~
     | The term 'nonsenseString' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

O exemplo a seguir inclui uma `trap` instrução que exibe o erro usando a `$_` variável automática:

```powershell
function TrapTest {
    trap {"Error found: $_"}
    nonsenseString
}

TrapTest
```

A execução desta versão da função retorna o seguinte:

```Output
Error found: The term 'nonsenseString' is not recognized as the name of a
cmdlet, function, script file, or operable program. Check the spelling of the
name, or if a path was included, verify that the path is correct and try again.
nonsenseString:
Line |
   3 |      nonsenseString
     |      ~~~~~~~~~~~~~~
     | The term 'nonsenseString' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

> [!IMPORTANT]
> `trap` as instruções podem ser definidas em qualquer lugar dentro de um determinado escopo, mas sempre se aplicam a todas as instruções nesse escopo. Em tempo de execução, `trap` as instruções em um bloco são definidas antes de qualquer outra instrução ser executada. No JavaScript, isso é conhecido como [guindaste](https://wikipedia.org/wiki/JavaScript_syntax#hoisting). Isso significa que `trap` as instruções se aplicam a todas as instruções nesse bloco, mesmo que a execução não tenha sido avançada após o ponto no qual elas são definidas. Por exemplo, definir um `trap` no final de um script e lançar um erro na primeira instrução ainda dispara isso `trap` .

### <a name="trapping-specific-errors"></a>Interceptando erros específicos

Um script ou comando pode ter várias `trap` instruções. Um `trap` pode ser definido para lidar com erros específicos.

O exemplo a seguir é uma `trap` instrução que intercepta o erro específico **CommandNotFoundException** :

```powershell
trap [System.Management.Automation.CommandNotFoundException]
    {"Command error trapped"}
```

Quando uma função ou script encontra uma cadeia de caracteres que não corresponde a um comando conhecido, essa `trap` instrução exibe a cadeia de caracteres "erro de comando interceptado".
Depois de executar a `trap` lista de instruções, o PowerShell grava o objeto de erro no fluxo de erros e, em seguida, continua o script.

O PowerShell usa tipos de exceção .NET. O exemplo a seguir especifica o tipo de erro **System. Exception** :

```powershell
trap [System.Exception] {"An error trapped"}
```

O tipo de erro **CommandNotFoundException** herda do tipo **System. Exception** . Essa instrução intercepta um erro que é criado por um comando desconhecido. Ele também intercepta outros tipos de erro.

Você pode ter mais de uma `trap` instrução em um script. Cada tipo de erro pode ser interceptado por apenas uma `trap` instrução. Quando ocorre um erro de encerramento, o PowerShell procura o `trap` com a correspondência mais específica, começando no escopo atual de execução.

O exemplo de script a seguir contém um erro. O script inclui uma `trap` instrução geral que intercepta qualquer erro de encerramento e uma `trap` instrução específica que especifica o tipo **CommandNotFoundException** .

```powershell
trap {"Other terminating error trapped" }
trap [System.Management.Automation.CommandNotFoundException] {
  "Command error trapped"
}
nonsenseString
```

A execução desse script produz o seguinte resultado:

```Output
Command error trapped
nonsenseString:
Line |
   5 |  nonsenseString
     |  ~~~~~~~~~~~~~~
     | The term 'nonsenseString' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

Como o PowerShell não reconhece "não-Sense" como um cmdlet ou outro item, ele retorna um erro **CommandNotFoundException** . Esse erro de encerramento é interceptado pela `trap` instrução específica.

O exemplo de script a seguir contém as mesmas `trap` instruções com um erro diferente:

```powershell
trap {"Other terminating error trapped" }
trap [System.Management.Automation.CommandNotFoundException]
    {"Command error trapped"}
1/$null
```

A execução desse script produz o seguinte resultado:

```Output
Other terminating error trapped
RuntimeException:
Line |
   4 |  1/$null
     |  ~~~~~~~
     | Attempted to divide by zero.
```

A tentativa de dividir por zero não cria um erro **CommandNotFoundException** . Em vez disso, esse erro é interceptado pela outra `trap` instrução, que intercepta qualquer erro de encerramento.

### <a name="trapping-errors-and-scope"></a>Interceptando erros e escopo

Se um erro de encerramento ocorrer no mesmo escopo que a `trap` instrução, o PowerShell executará a lista de instruções definidas pelo `trap` . A execução continua na instrução após o erro. Se a `trap` instrução estiver em um escopo diferente do erro, a execução continuará na próxima instrução que está no mesmo escopo que a `trap` instrução.

Por exemplo, se ocorrer um erro em uma função e a `trap` instrução estiver na função, o script continuará na próxima instrução. O script a seguir contém um erro e uma `trap` instrução:

```powershell
function function1 {
    trap { "An error: " }
    NonsenseString
    "function1 was completed"
}

function1
```

A execução desse script produz o seguinte resultado:

```Output
An error:
NonsenseString:
Line |
   3 |      NonsenseString
     |      ~~~~~~~~~~~~~~
     | The term 'NonsenseString' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
function1 was completed
```

A `trap` instrução na função intercepta o erro. Depois de exibir a mensagem, o PowerShell retoma a execução da função. Observe que `Function1` foi concluída.

Compare isso com o exemplo a seguir, que tem o mesmo erro e `trap` instrução. Neste exemplo, a `trap` instrução ocorre fora da função:

```powershell
function function2 {
    NonsenseString
    "function2 was completed"
}

trap { "An error: " }

function2
```

A execução da `Function2` função produz o seguinte resultado:

```Output
An error:
NonsenseString:
Line |
   2 |      NonsenseString
     |      ~~~~~~~~~~~~~~
     | The term 'NonsenseString' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

Neste exemplo, o comando "function2 foi concluído" não foi executado. Em ambos os exemplos, o erro de encerramento ocorre dentro da função. Neste exemplo, no entanto, a `trap` instrução está fora da função. O PowerShell não volta à função depois que a `trap` instrução é executada.

> [!CAUTION]
> Quando várias interceptações são definidas para a mesma condição de erro, o primeiro `trap` definido lexicalmente (mais alto no escopo) é usado.

No exemplo a seguir, somente o `trap` com "Opa 1" é executado.

```powershell
Remove-Item -ErrorAction Stop ThisFileDoesNotExist
trap { "whoops 1"; continue }
trap { "whoops 2"; continue }
```

> [!IMPORTANT]
> Uma instrução de interceptação é delimitada para onde ela é compilada. Se você tiver uma `trap` instrução dentro de um script de origem de função ou ponto, quando o script de função ou ponto tiver sido encerrado, todas as `trap` instruções dentro serão removidas.

### <a name="using-the-break-and-continue-keywords"></a>Usando as palavras-chave break e continue

Você pode usar as `break` `continue` palavras-chave e em uma `trap` instrução para determinar se um script ou comando continua a ser executado após um erro de encerramento.

Se você incluir uma `break` instrução em uma `trap` lista de instruções, o PowerShell interromperá a função ou o script. A seguinte função de exemplo usa a `break` palavra-chave em uma `trap` instrução:

```powershell
function break_example {
    trap {
        "Error trapped"
        break
    }
    1/$null
    "Function completed."
}

break_example
```

```Output
Error trapped
ParentContainsErrorRecordException:
Line |
   6 |      1/$null
     |      ~~~~~~~
     | Attempted to divide by zero.
```

Como a `trap` instrução incluía a `break` palavra-chave, a função não continua a ser executada e a linha "função concluída" não é executada.

Se você incluir uma `continue` palavra-chave em uma `trap` instrução, o PowerShell será retomado após a instrução que causou o erro, assim como faria sem `break` ou `continue` . Com a `continue` palavra-chave, no entanto, o PowerShell não grava um erro no fluxo de erros.

A seguinte função de exemplo usa a `continue` palavra-chave em uma `trap` instrução:

```powershell
function continue_example {
    trap {
        "Error trapped"
        continue
    }
    1/$null
    "Function completed."
}

continue_example
```

```Output
Error trapped
Function completed.
```

A função é retomada depois que o erro é interceptado e a instrução "função concluída" é executada. Nenhum erro é gravado no fluxo de erro.

## <a name="notes"></a>Observações

`trap` as instruções fornecem uma maneira simples de garantir amplamente a manipulação de todos os erros de encerramento dentro de um escopo. Para tratamento de erros mais refinado, use `try` / `catch` blocos em que as interceptações são definidas usando `catch` instruções. As `catch` instruções se aplicam somente ao código dentro da `try` instrução associada. Para obter mais informações, consulte [about_Try_Catch_Finally](about_Try_Catch_Finally.md).

## <a name="see-also"></a>Confira também

[about_Break](about_Break.md)

[about_Continue](about_Continue.md)

[about_Scopes](about_Scopes.md)

[about_Throw](about_Throw.md)

[about_Try_Catch_Finally](about_Try_Catch_Finally.md)
