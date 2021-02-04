---
description: Descreve regras para usar aspas simples e duplas no PowerShell.
Locale: en-US
ms.date: 12/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_quoting_rules?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Quoting_Rules
ms.openlocfilehash: 27d5909c1381c0d221690b353a308680643ecad5
ms.sourcegitcommit: 9a86cac80402d8193147058d4ba50e07b26059dd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97490747"
---
# <a name="about-quoting-rules"></a>Sobre regras de cotação

## <a name="short-description"></a>Descrição breve
Descreve regras para usar aspas simples e duplas no PowerShell.

## <a name="long-description"></a>Descrição longa

Aspas são usadas para especificar uma cadeia de caracteres literal. Você pode colocar uma cadeia de caracteres entre aspas simples ( `'` ) ou aspas duplas ( `"` ).

Aspas também são usadas para criar uma _cadeia de caracteres aqui_. Uma cadeia de caracteres aqui é uma cadeia de caracteres entre aspas simples ou com aspas duplas em que as aspas são interpretadas literalmente. Uma cadeia de caracteres aqui pode abranger várias linhas. Todas as linhas em uma cadeia de caracteres aqui são interpretadas como cadeias de caracteres, mesmo que não sejam colocadas entre aspas.

Em comandos para computadores remotos, aspas definem as partes do comando que são executadas no computador remoto. Em uma sessão remota, as aspas também determinam se as variáveis em um comando são interpretadas primeiro no computador local ou no computador remoto.

## <a name="single-and-double-quoted-strings"></a>Cadeias de caracteres de aspas simples e duplas

Uma cadeia de caracteres entre aspas duplas é uma cadeia de caracteres _expansível_ . Os nomes de variáveis precedidos por um cifrão ( `$` ) são substituídos pelo valor da variável antes que a cadeia de caracteres seja passada para o comando para processamento.

Por exemplo:

```powershell
$i = 5
"The value of $i is $i."
```

A saída desse comando é:

```Output
The value of 5 is 5.
```

Além disso, em uma cadeia de caracteres com aspas duplas, as expressões são avaliadas e o resultado é inserido na cadeia de caracteres. Por exemplo:

```powershell
"The value of $(2+3) is 5."
```

A saída desse comando é:

```Output
The value of 5 is 5.
```

Uma cadeia de caracteres entre aspas simples é uma cadeia de caracteres _textual_ . A cadeia de caracteres é passada para o comando exatamente conforme você o digita. Nenhuma substituição é executada.
Por exemplo:

```powershell
$i = 5
'The value of $i is $i.'
```

A saída desse comando é:

```Output
The value $i is $i.
```

Da mesma forma, as expressões em cadeias de caracteres entre aspas simples não são avaliadas. Eles são interpretados como literais. Por exemplo:

```powershell
'The value of $(2+3) is 5.'
```

A saída desse comando é:

```Output
The value of $(2+3) is 5.
```

Para evitar a substituição de um valor de variável em uma cadeia de caracteres com aspas duplas, use o caractere de acento grave ( `` ` `` ) (ASCII 96), que é o caractere de escape do PowerShell.

No exemplo a seguir, o caractere de acento grave que precede a primeira `$i` variável impede que o PowerShell substitua o nome da variável por seu valor.
Por exemplo:

```powershell
$i = 5
"The value of `$i is $i."
```

A saída desse comando é:

```Output
The value $i is 5.
```

Para que as aspas duplas apareçam em uma cadeia de caracteres, coloque a cadeia de caracteres inteira entre aspas simples. Por exemplo:

```powershell
'As they say, "live and learn."'
```

A saída desse comando é:

```Output
As they say, "live and learn."
```

Você também pode colocar uma cadeia de caracteres entre aspas simples em uma cadeia de caracteres com aspas duplas. Por exemplo:

```powershell
"As they say, 'live and learn.'"
```

A saída desse comando é:

```Output
As they say, 'live and learn.'
```

Ou, clique duas vezes nas aspas ao contrário de uma frase entre aspas duplas. Por exemplo:

```powershell
"As they say, ""live and learn."""
```

A saída desse comando é:

```Output
As they say, "live and learn."
```

Para incluir uma aspa simples em uma cadeia de caracteres entre aspas simples, use uma segunda aspa simples consecutiva. Por exemplo:

```powershell
'don''t'
```

A saída desse comando é:

```Output
don't
```

Para forçar o PowerShell a interpretar uma aspa dupla literalmente, use um caractere de acento grave. Isso impede que o PowerShell interprete a aspa como um delimitador de cadeia de caracteres. Por exemplo:

```powershell
PS> "Use a quotation mark (`") to begin a string."
Use a quotation mark (") to begin a string.
PS> 'Use a quotation mark (`") to begin a string.'
Use a quotation mark (`") to begin a string.
```

Como o conteúdo das cadeias de caracteres entre aspas simples é interpretado literalmente, o caractere de acento grave é tratado como um caractere literal e exibido na saída.

## <a name="here-strings"></a>Aqui-cadeias de caracteres

As regras de cotação para as cadeias de caracteres aqui são um pouco diferentes.

Uma cadeia de caracteres aqui é uma cadeia de caracteres entre aspas simples ou com aspas duplas em que as aspas são interpretadas literalmente. Uma cadeia de caracteres aqui pode abranger várias linhas. Todas as linhas em uma cadeia de caracteres aqui são interpretadas como cadeias de texto, mesmo que não sejam colocadas entre aspas.

Como cadeias de caracteres regulares, as variáveis são substituídas por seus valores em cadeias de caracteres aqui com aspas duplas. Em cadeias de caracteres aqui entre aspas simples, as variáveis não são substituídas por seus valores.

Você pode usar as cadeias de caracteres aqui para qualquer texto, mas elas são particularmente úteis para os seguintes tipos de texto:

- Texto que contém aspas literais
- Várias linhas de texto, como o texto em um HTML ou XML
- O texto de ajuda para um documento de script ou função

Uma cadeia de caracteres here pode ter qualquer um dos formatos a seguir, onde `<Enter>` representa o caractere oculto de linhagem ou novas linhas que é adicionado quando você pressiona a tecla <kbd>Enter</kbd> .

Aspas duplas:

```
@"<Enter>
<string> [string] ...<Enter>
"@
```

Aspas simples:

```
@'<Enter>
<string> [string] ...<Enter>
'@
```

Em qualquer formato, a aspa de fechamento deve ser o primeiro caractere na linha.

Uma cadeia de caracteres aqui contém todo o texto entre os dois caracteres ocultos. Na cadeia de caracteres here, todas as aspas são interpretadas literalmente. Por exemplo:

```powershell
@"
For help, type "get-help"
"@
```

A saída desse comando é:

```Output
For help, type "get-help"
```

O uso de uma cadeia de caracteres aqui pode simplificar o uso de uma cadeia de caracteres em um comando. Por exemplo:

```powershell
@"
Use a quotation mark (') to begin a string.
"@
```

A saída desse comando é:

```Output
Use a quotation mark (') to begin a string.
```

Em cadeias de caracteres aqui entre aspas simples, as variáveis são interpretadas literalmente e reproduzidas exatamente. Por exemplo:

```powershell
@'
The $profile variable contains the path
of your PowerShell profile.
'@
```

A saída desse comando é:

```Output
The $profile variable contains the path
of your PowerShell profile.
```

Em cadeias de caracteres com aspas duplas, as variáveis são substituídas por seus valores. Por exemplo:

```powershell
@"
Even if you have not created a profile,
the path of the profile file is:
$profile.
"@
```

A saída desse comando é:

```Output
Even if you have not created a profile,
the path of the profile file is:
C:\Users\User1\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1.
```

Aqui – as cadeias de caracteres normalmente são usadas para atribuir várias linhas a uma variável. Por exemplo, a cadeia de caracteres aqui a seguir atribui uma página de XML à variável $page.

```powershell
$page = [XML] @"
<command:command xmlns:maml="http://schemas.microsoft.com/maml/2004/10"
xmlns:command="http://schemas.microsoft.com/maml/dev/command/2004/10"
xmlns:dev="http://schemas.microsoft.com/maml/dev/2004/10">
<command:details>
        <command:name>
               Format-Table
        </command:name>
        <maml:description>
            <maml:para>Formats the output as a table.</maml:para>
        </maml:description>
        <command:verb>format</command:verb>
        <command:noun>table</command:noun>
        <dev:version></dev:version>
</command:details>
...
</command:command>
"@
```

Aqui-as cadeias de caracteres também são um formato conveniente para entrada para o `ConvertFrom-StringData` cmdlet, que converte as cadeias de caracteres aqui em tabelas de hash.
Para obter mais informações, consulte `ConvertFrom-StringData`.

## <a name="see-also"></a>Confira também

[about_Special_Characters](about_Special_Characters.md)

[ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)
