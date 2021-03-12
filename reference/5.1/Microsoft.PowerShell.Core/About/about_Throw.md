---
description: Descreve a palavra-chave Throw, que gera um erro de terminação.
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_throw?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Throw
ms.openlocfilehash: e573722154fff99363b26806064ec17c8903bfd8
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103194169"
---
# <a name="about-throw"></a>Sobre o throw

## <a name="short-description"></a>DESCRIÇÃO BREVE

Descreve a palavra-chave Throw, que gera um erro de terminação.

## <a name="long-description"></a>DESCRIÇÃO LONGA

A palavra-chave Throw causa um erro de encerramento. Você pode usar a palavra-chave Throw para interromper o processamento de um comando, uma função ou um script.

Por exemplo, você pode usar a palavra-chave Throw no bloco de script de uma instrução If para responder a uma condição ou no bloco catch de uma instrução try-catch-finally. Você também pode usar a palavra-chave Throw em uma declaração de parâmetro para tornar obrigatório um parâmetro de função.

A palavra-chave Throw pode gerar qualquer objeto, como uma cadeia de caracteres de mensagem de usuário ou o objeto que causou o erro.

## <a name="syntax"></a>SYNTAX

A sintaxe da palavra-chave Throw é a seguinte:

```powershell
throw [<expression>]
```

A expressão na sintaxe Throw é opcional. Quando a instrução Throw não aparece em um bloco catch e não inclui uma expressão, ela gera um erro ScriptHalted.

```powershell
C:\PS> throw

ScriptHalted
At line:1 char:6
+ throw <<<<
+ CategoryInfo          : OperationStopped: (:) [], RuntimeException
+ FullyQualifiedErrorId : ScriptHalted
```

Se a palavra-chave Throw for usada em um bloco catch sem uma expressão, ela lançará a RuntimeException atual novamente. Para obter mais informações, consulte about_Try_Catch_Finally.

## <a name="throwing-a-string"></a>LANÇANDO UMA CADEIA DE CARACTERES

A expressão opcional em uma instrução Throw pode ser uma cadeia de caracteres, conforme mostrado no exemplo a seguir:

```powershell
C:\PS> throw "This is an error."

This is an error.
At line:1 char:6
+ throw <<<<  "This is an error."
+ CategoryInfo          : OperationStopped: (This is an error.:String) [], R
untimeException
+ FullyQualifiedErrorId : This is an error.
```

## <a name="throwing-other-objects"></a>LANÇANDO OUTROS OBJETOS

A expressão também pode ser um objeto que gera o objeto que representa o processo do PowerShell, conforme mostrado no exemplo a seguir:

```powershell
C:\PS> throw (get-process PowerShell)

System.Diagnostics.Process (PowerShell)
At line:1 char:6
+ throw <<<<  (get-process PowerShell)
+ CategoryInfo          : OperationStopped: (System.Diagnostics.Process (Pow
erShell):Process) [],
RuntimeException
+ FullyQualifiedErrorId : System.Diagnostics.Process (PowerShell)
```

Você pode usar a propriedade TargetObject do objeto ErrorRecord no $error variável automática para examinar o erro.

```powershell
C:\PS> $error[0].targetobject

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
319      26    61016      70864   568     3.28   5548 PowerShell
```

Você também pode lançar um objeto ErrorRecord ou uma exceção de estrutura de Microsoft .NET. O exemplo a seguir usa a palavra-chave Throw para lançar um objeto System. FormatException.

```powershell
C:\PS> $formatError = new-object system.formatexception

C:\PS> throw $formatError

One of the identified items was in an invalid format.
At line:1 char:6
+ throw <<<<  $formatError
+ CategoryInfo          : OperationStopped: (:) [], FormatException
+ FullyQualifiedErrorId : One of the identified items was in an invalid
format.
```

## <a name="resulting-error"></a>ERRO RESULTANTE

A palavra-chave Throw pode gerar um objeto ErrorRecord. A propriedade Exception do objeto ErrorRecord contém um objeto RuntimeException. O restante do objeto ErrorRecord e o objeto RuntimeException variam com o objeto que a palavra-chave Throw gera.

O objeto RunTimeexception é encapsulado em um objeto ErrorRecord e o objeto ErrorRecord é salvo automaticamente no $Error variável automática.

## <a name="using-throw-to-create-a-mandatory-parameter"></a>USANDO THROW PARA CRIAR UM PARÂMETRO OBRIGATÓRIO

Você pode usar a palavra-chave Throw para tornar obrigatório um parâmetro de função.

Essa é uma alternativa ao uso do parâmetro obrigatório da palavra-chave Parameter. Quando você usa o parâmetro obrigatório, o sistema solicita ao usuário o valor de parâmetro necessário. Quando você usa a palavra-chave Throw, o comando para e exibe o registro de erro.

Por exemplo, a palavra-chave Throw na subexpressão de parâmetro torna o parâmetro Path um parâmetro necessário na função.

Nesse caso, a palavra-chave Throw gera uma cadeia de caracteres de mensagem, mas é a presença da palavra-chave Throw que gera o erro de encerramento se o parâmetro Path não for especificado. A expressão a seguir Throw é opcional.

```powershell
function Get-XMLFiles
{
  param ($path = $(throw "The Path parameter is required."))
  dir -path $path\*.xml -recurse |
    sort lastwritetime |
      ft lastwritetime, attributes, name  -auto
}
```

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Break](about_Break.md)

[about_Continue](about_Continue.md)

[about_Scopes](about_Scopes.md)

[about_Trap](about_Trap.md)

[about_Try_Catch_Finally](about_Try_Catch_Finally.md)
