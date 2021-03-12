---
description: Descreve a palavra-chave Throw, que gera um erro de terminação.
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_throw?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Throw
ms.openlocfilehash: f54ec305c18d4a43888af351f2e130b104b4146e
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103194276"
---
# <a name="about-throw"></a>Sobre o throw

## <a name="short-description"></a>Descrição breve
Descreve a palavra-chave Throw, que gera um erro de terminação.

## <a name="long-description"></a>Descrição longa

A palavra-chave Throw causa um erro de encerramento. Você pode usar a palavra-chave Throw para interromper o processamento de um comando, uma função ou um script.

Por exemplo, você pode usar a palavra-chave Throw no bloco de script de uma instrução If para responder a uma condição ou no bloco catch de uma instrução try-catch-finally. Você também pode usar a palavra-chave Throw em uma declaração de parâmetro para tornar obrigatório um parâmetro de função.

A palavra-chave Throw pode gerar qualquer objeto, como uma cadeia de caracteres de mensagem de usuário ou o objeto que causou o erro.

## <a name="syntax"></a>Sintaxe

A sintaxe da palavra-chave Throw é a seguinte:

```powershell
throw [<expression>]
```

A expressão na sintaxe Throw é opcional. Quando a instrução Throw não aparece em um bloco catch e não inclui uma expressão, ela gera um erro ScriptHalted.

```powershell
C:\PS> throw

Exception: ScriptHalted
```

Se a palavra-chave Throw for usada em um bloco catch sem uma expressão, ela lançará a RuntimeException atual novamente. Para obter mais informações, consulte about_Try_Catch_Finally.

## <a name="throwing-a-string"></a>Lançando uma cadeia de caracteres

A expressão opcional em uma instrução Throw pode ser uma cadeia de caracteres, conforme mostrado no exemplo a seguir:

```powershell
C:\PS> throw "This is an error."

Exception: This is an error.
```

## <a name="throwing-other-objects"></a>Lançando outros objetos

A expressão também pode ser um objeto que gera o objeto que representa o processo do PowerShell, conforme mostrado no exemplo a seguir:

```powershell
C:\PS> throw (get-process Pwsh)

Exception: System.Diagnostics.Process (pwsh) System.Diagnostics.Process (pwsh) System.Diagnostics.Process (pwsh)
```

Você pode usar a propriedade TargetObject do objeto ErrorRecord no $error variável automática para examinar o erro.

```powershell
C:\PS> $error[0].targetobject

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    125   174.44     229.57      23.61    1548   2 pwsh
     63    44.07      81.95       1.75    1732   2 pwsh
     63    43.32      77.65       1.48    9092   2 pwsh
```

Você também pode lançar um objeto ErrorRecord ou uma exceção .NET. O exemplo a seguir usa a palavra-chave Throw para lançar um objeto System. FormatException.

```powershell
C:\PS> $formatError = new-object system.formatexception

C:\PS> throw $formatError

OperationStopped: One of the identified items was in an invalid format.
```

## <a name="the-resulting-error"></a>O erro resultante

A palavra-chave Throw pode gerar um objeto ErrorRecord. A propriedade Exception do objeto ErrorRecord contém um objeto RuntimeException. O restante do objeto ErrorRecord e o objeto RuntimeException variam com o objeto que a palavra-chave Throw gera.

O objeto RunTimeexception é encapsulado em um objeto ErrorRecord e o objeto ErrorRecord é salvo automaticamente no $Error variável automática.

## <a name="using-throw-to-create-a-mandatory-parameter"></a>Usando throw para criar um parâmetro obrigatório

Ao contrário das versões anteriores do PowerShell, não use a palavra-chave Throw para validação de parâmetro. Consulte [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md) da maneira correta.

## <a name="see-also"></a>Confira também

- [about_Break](about_Break.md)
- [about_Continue](about_Continue.md)
- [about_Scopes](about_Scopes.md)
- [about_Trap](about_Trap.md)
- [about_Try_Catch_Finally](about_Try_Catch_Finally.md)
