---
description: Descreve como usar os `Try` blocos, `Catch` e `Finally` para lidar com erros de encerramento.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 04/01/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_try_catch_finally?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Try_Catch_Finally
ms.openlocfilehash: 1bb6974e1ba42861a4f411777be237685d2becbc
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195466"
---
# <a name="about-try-catch-finally"></a>Sobre try catch finalmente

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve como usar os `Try` blocos, `Catch` e `Finally` para lidar com erros de encerramento.

## <a name="long-description"></a>DESCRIÇÃO LONGA

Use `Try` os `Catch` blocos, e `Finally` para responder ou manipular erros de encerramento em scripts. A `Trap` instrução também pode ser usada para lidar com erros de encerramento em scripts. Para obter mais informações, consulte [about_Trap](about_Trap.md).

Um erro de encerramento interrompe a execução de uma instrução. Se o PowerShell não tratar um erro de encerramento de alguma forma, o PowerShell também interromperá a execução da função ou do script usando o pipeline atual. Em outras linguagens, como C \# , os erros de encerramento são chamados de exceções.

Use o `Try` bloco para definir uma seção de um script no qual você deseja que o PowerShell monitore os erros. Quando ocorre um erro dentro do `Try` bloco, o erro é salvo primeiro na `$Error` variável automática. Em seguida, o PowerShell procura um `Catch` bloco para manipular o erro. Se a `Try` instrução não tiver um bloco correspondente `Catch` , o PowerShell continuará procurando um `Catch` bloco ou uma `Trap` instrução apropriada nos escopos pai. Depois `Catch` que um bloco for concluído ou se nenhum `Catch` bloco ou `Trap` instrução apropriado for encontrado, o `Finally` bloco será executado. Se o erro não puder ser tratado, o erro será gravado no fluxo de erro.

Um `Catch` bloco pode incluir comandos para acompanhar o erro ou para recuperar o fluxo esperado do script. Um `Catch` bloco pode especificar quais tipos de erro ele captura. Uma `Try` instrução pode incluir vários `Catch` blocos para diferentes tipos de erros.

Um `Finally` bloco pode ser usado para liberar todos os recursos que não são mais necessários para o seu script.

`Try`, `Catch` e se `Finally` assemelham às `Try` `Catch` `Finally` palavras-chave, e usadas na \# linguagem de programação C.

### <a name="syntax"></a>SYNTAX

Uma `Try` instrução contém um `Try` bloco, zero ou mais `Catch` blocos e zero ou um `Finally` bloco. Uma `Try` instrução deve ter pelo menos um `Catch` bloco ou um `Finally` bloco.

O seguinte mostra a `Try` sintaxe de bloco:

```powershell
try {<statement list>}
```

A `Try` palavra-chave é seguida por uma lista de instruções entre chaves. Se ocorrer um erro de encerramento enquanto as instruções na lista de instruções estiverem sendo executadas, o script passará o objeto de erro do `Try` bloco para um `Catch` bloco apropriado.

O seguinte mostra a `Catch` sintaxe de bloco:

```powershell
catch [[<error type>][',' <error type>]*] {<statement list>}
```

Os tipos de erro aparecem entre colchetes. Os colchetes mais externos indicam que o elemento é opcional.

A `Catch` palavra-chave é seguida por uma lista opcional de especificações de tipo de erro e uma lista de instruções. Se ocorrer um erro de encerramento no `Try` bloco, o PowerShell procurará um `Catch` bloco apropriado. Se um for encontrado, as instruções no `Catch` bloco serão executadas.

O `Catch` bloco pode especificar um ou mais tipos de erro. Um tipo de erro é uma exceção de estrutura Microsoft .NET ou uma exceção que é derivada de uma exceção de .NET Framework. Um `Catch` bloco manipula erros da classe de exceção de .NET Framework especificada ou de qualquer classe derivada da classe especificada.

Se um `Catch` bloco especificar um tipo de erro, esse `Catch` bloco tratará desse tipo de erro. Se um `Catch` bloco não especificar um tipo de erro, esse `Catch` bloco tratará qualquer erro encontrado no `Try` bloco. Uma `Try` instrução pode incluir vários `Catch` blocos para os diferentes tipos de erro especificados.

O seguinte mostra a `Finally` sintaxe de bloco:

```powershell
finally {<statement list>}
```

A `Finally` palavra-chave é seguida por uma lista de instruções que é executada toda vez que o script é executado, mesmo que a `Try` instrução tenha sido executada sem erro ou um erro tenha sido detectado em uma `Catch` instrução.

Observe que pressionar <kbd>Ctrl</kbd> + <kbd>C</kbd> para o pipeline. Os objetos que são enviados para o pipeline não serão exibidos como saída. Portanto, se você incluir uma instrução a ser exibida, como "finally block tenha executado", ela não será exibida depois que você pressionar <kbd>Ctrl</kbd> + <kbd>C</kbd>, mesmo que o `Finally` bloco seja executado.

### <a name="catching-errors"></a>ERROS DE CAPTURA

O script de exemplo a seguir mostra um `Try` bloco com um `Catch` bloco:

```powershell
try { NonsenseString }
catch { "An error occurred." }
```

A `Catch` palavra-chave deve seguir imediatamente o `Try` bloco ou outro `Catch` bloco.

O PowerShell não reconhece "não-Sense" como um cmdlet ou outro item.
A execução desse script retorna o seguinte resultado:

```powershell
An error occurred.
```

Quando o script encontra "não sensorstring", ele causa um erro de encerramento. O `Catch` bloco trata o erro executando a lista de instruções dentro do bloco.

### <a name="using-multiple-catch-statements"></a>USANDO VÁRIAS INSTRUÇÕES CATCH

Uma `Try` instrução pode ter qualquer número de `Catch` blocos. Por exemplo, o script a seguir tem um `Try` bloco que `MyDoc.doc` é baixado e contém dois `Catch` blocos:

```powershell
try {
   $wc = new-object System.Net.WebClient
   $wc.DownloadFile("http://www.contoso.com/MyDoc.doc","c:\temp\MyDoc.doc")
}
catch [System.Net.WebException],[System.IO.IOException] {
    "Unable to download MyDoc.doc from http://www.contoso.com."
}
catch {
    "An error occurred that could not be resolved."
}

```

O primeiro `Catch` bloco manipula erros dos tipos **System .net. WebException** e **System. IO. IOException** . O segundo `Catch` bloco não especifica um tipo de erro. O segundo `Catch` bloco manipula quaisquer outros erros de encerramento que ocorrem.

O PowerShell corresponde aos tipos de erro por herança. Um `Catch` bloco manipula erros da classe de exceção de .NET Framework especificada ou de qualquer classe derivada da classe especificada. O exemplo a seguir contém um `Catch` bloco que captura um erro "comando não encontrado":

```powershell
catch [System.Management.Automation.CommandNotFoundException]
{"Inherited Exception" }
```

O tipo de erro especificado, **CommandNotFoundException** , é herdado do tipo de **System.SystemException** . O exemplo a seguir também captura um erro de comando não encontrado:

```powershell
catch [System.SystemException] {"Base Exception" }
```

Esse `Catch` bloco manipula o erro "comando não encontrado" e outros erros que herdam do tipo **SystemException** .

Se você especificar uma classe de erro e uma de suas classes derivadas, coloque o `Catch` bloco para a classe derivada antes do `Catch` bloco da classe geral.

### <a name="using-traps-in-a-try-catch"></a>Usando interceptações em uma tentativa catch

Quando ocorre um erro de encerramento em um `Try` bloco com um `Trap` definido dentro do `Try` bloco, mesmo que haja um bloco correspondente `Catch` , a `Trap` instrução assume o controle.

Se `Trap` existir um em um bloco maior do que o `Try` , e não houver nenhum `Catch` bloco correspondente no escopo atual, o `Trap` assumirá o controle, mesmo que qualquer escopo pai tenha um `Catch` bloco correspondente.

### <a name="accessing-exception-information"></a>ACESSANDO INFORMAÇÕES DE EXCEÇÃO

Em um `Catch` bloco, o erro atual pode ser acessado usando `$_` , que também é conhecido como `$PSItem` . O objeto é do tipo **ErrorRecord** .

```powershell
try { NonsenseString }
catch {
  Write-Host "An error occurred:"
  Write-Host $_
}
```

A execução desse script retorna o seguinte resultado:

```Output
An Error occurred:
The term 'NonsenseString' is not recognized as the name of a cmdlet, function,
script file, or operable program. Check the spelling of the name, or if a path
was included, verify that the path is correct and try again.
```

Há propriedades adicionais que podem ser acessadas, como **ScriptStackTrace** , **Exception** e **ErrorDetails** .  Por exemplo, se alterarmos o script para o seguinte:

```powershell
try { NonsenseString }
catch {
  Write-Host "An error occurred:"
  Write-Host $_.ScriptStackTrace
}
```

O resultado será semelhante a:

```
An Error occurred:
at <ScriptBlock>, <No file>: line 2
```

### <a name="freeing-resources-by-using-finally"></a>LIBERANDO RECURSOS USANDO FINALLY

Para liberar recursos usados por um script, adicione um `Finally` bloco após os `Try` `Catch` blocos e. As `Finally` instruções de bloco são executadas independentemente de o `Try` bloco encontrar um erro de encerramento. O PowerShell executa o `Finally` bloco antes que o script seja encerrado ou antes que o bloco atual saia do escopo.

Um `Finally` bloco é executado mesmo se você usar <kbd>Ctrl</kbd> + <kbd>C</kbd> para interromper o script. Um `Finally` bloco também será executado se uma palavra-chave Exit parar o script dentro de um `Catch` bloco.

### <a name="see-also"></a>CONSULTE TAMBÉM

[about_Break](about_Break.md)

[about_Continue](about_Continue.md)

[about_Scopes](about_Scopes.md)

[about_Throw](about_Throw.md)

[about_Trap](about_Trap.md)
