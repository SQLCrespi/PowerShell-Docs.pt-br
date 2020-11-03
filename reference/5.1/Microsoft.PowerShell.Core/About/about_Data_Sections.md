---
description: Explica as seções de dados, que isolam cadeias de caracteres de texto e outros dados somente leitura da lógica de script.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_data_sections?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Data_Sections
ms.openlocfilehash: d45339bae42b1131e1dfb9618413a34e250a578e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196226"
---
# <a name="about-data-sections"></a>Sobre seções de dados

## <a name="short-description"></a>Descrição breve
Explica as seções de dados, que isolam cadeias de caracteres de texto e outros dados somente leitura da lógica de script.

## <a name="long-description"></a>Descrição longa

Os scripts projetados para o PowerShell podem ter uma ou mais seções de dados que contêm apenas dados. Você pode incluir uma ou mais seções de dados em qualquer script, função ou função avançada. O conteúdo da seção de dados é restrito a um subconjunto especificado da linguagem de script do PowerShell.

Separar dados da lógica de código torna mais fácil identificar e gerenciar a lógica e os dados. Ele permite que você tenha arquivos de recurso de cadeia de caracteres separados para texto, como mensagens de erro e cadeias de caracteres de ajuda. Ele também isola a lógica de código, que facilita os testes de segurança e validação.

No PowerShell, a seção de dados é usada para dar suporte à internacionalização de script.
Você pode usar seções de dados para facilitar a tarefa de isolar, localizar e processar cadeias de caracteres que serão convertidas em muitas linguagens de interface do usuário.

A seção de dados é um recurso do PowerShell 2,0. Scripts com seções de dados não serão executados no PowerShell 1,0 sem revisão.

### <a name="syntax"></a>Syntax

A sintaxe de uma seção de dados é a seguinte:

```
DATA [<variable-name>] [-supportedCommand <cmdlet-name>] {
    <Permitted content>
}
```

A palavra-chave data é necessária. Não diferencia maiúsculas de minúsculas. O conteúdo permitido é limitado aos seguintes elementos:

- Todos os operadores do PowerShell, exceto `-match`
- `If``Else`instruções, e `ElseIf`
- As seguintes variáveis automáticas:,,, `$PsCulture` `$PsUICulture` `$True` `$False` e `$Null`
- Comentários
- Pipelines
- Instruções separadas por ponto e vírgula ( `;` )
- Literais, como o seguinte:

  ```powershell
  a
  1
  1,2,3
  "PowerShell 2.0"
  @( "red", "green", "blue" )
  @{ a = 0x1; b = "great"; c ="script" }
  [XML] @'
  <p> Hello, World </p>
  '@
  ```

- Cmdlets que são permitidos em uma seção de dados. Por padrão, somente o `ConvertFrom-StringData` cmdlet é permitido.
- Cmdlets que você permite em uma seção de dados usando o `-SupportedCommand` parâmetro.

Ao usar o `ConvertFrom-StringData` cmdlet em uma seção de dados, você pode colocar os pares de chave-valor em cadeias de caracteres entre aspas simples ou com aspas duplas ou em cadeias de caracteres de aspas simples ou com aspas duplas. No entanto, as cadeias de caracteres que contêm variáveis e subexpressões devem ser colocadas entre cadeias de caracteres entre aspas simples ou em cadeias de caracteres entre aspas simples para que as variáveis não sejam expandidas e as subexpressãos não sejam executáveis.

### <a name="-supportedcommand"></a>-SupportedCommand

O `-SupportedCommand` parâmetro permite que você indique que um cmdlet ou função gera apenas dados. Ele foi projetado para permitir que os usuários incluam cmdlets e funções em uma seção de dados que foram escritos ou testados.

O valor de `-SupportedCommand` é uma lista separada por vírgulas de um ou mais nomes de cmdlet ou de função.

Por exemplo, a seção de dados a seguir inclui um cmdlet escrito pelo usuário, `Format-XML` , que formata dados em um arquivo XML:

```powershell
DATA -supportedCommand Format-Xml
{
    Format-Xml -Strings string1, string2, string3
}
```

### <a name="using-a-data-section"></a>Usando uma seção de dados

Para usar o conteúdo de uma seção de dados, atribua-a a uma variável e use a notação variável para acessar o conteúdo.

Por exemplo, a seção de dados a seguir contém um `ConvertFrom-StringData` comando que converte a cadeia de caracteres here em uma tabela de hash. A tabela de hash é atribuída à `$TextMsgs` variável.

A `$TextMsgs` variável não faz parte da seção de dados.

```powershell
$TextMsgs = DATA {
    ConvertFrom-StringData -StringData @'
Text001 = Windows 7
Text002 = Windows Server 2008 R2
'@
}
```

Para acessar as chaves e os valores na tabela de hash no `$TextMsgs` , use os comandos a seguir.

```powershell
$TextMsgs.Text001
$TextMsgs.Text002
```

Como alternativa, você pode colocar o nome da variável na definição da seção de dados. Por exemplo:

```powershell
DATA TextMsgs {
    ConvertFrom-StringData -StringData @'
Text001 = Windows 7
Text002 = Windows Server 2008 R2
'@
}

$TextMsgs
```

O resultado é o mesmo que o exemplo anterior.

```Output
Name                           Value
----                           -----
Text001                        Windows 7
Text002                        Windows Server 2008 R2
```

### <a name="examples"></a>Exemplos

Cadeias de dados simples.

```powershell
DATA {
    "Thank you for using my PowerShell Organize.pst script."
    "It is provided free of charge to the community."
    "I appreciate your comments and feedback."
}
```

Cadeias de caracteres que incluem variáveis permitidas.

```powershell
DATA {
    if ($null) {
        "To get help for this cmdlet, type get-help new-dictionary."
    }
}
```

Uma cadeia de caracteres aqui entre aspas simples que usa o `ConvertFrom-StringData` cmdlet:

```powershell
DATA {
    ConvertFrom-StringData -stringdata @'
Text001 = Windows 7
Text002 = Windows Server 2008 R2
'@
}
```

Uma cadeia de caracteres aqui com aspas duplas que usa o `ConvertFrom-StringData` cmdlet:

```powershell
DATA  {
    ConvertFrom-StringData -stringdata @"
Msg1 = To start, press any key.
Msg2 = To exit, type "quit".
"@
}
```

Uma seção de dados que inclui um cmdlet escrito pelo usuário que gera dados:

```powershell
DATA -supportedCommand Format-XML {
    Format-Xml -strings string1, string2, string3
}
```

## <a name="see-also"></a>Consulte Também

[about_Automatic_Variables](about_Automatic_Variables.md)

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Hash_Tables](about_Hash_Tables.md)

[about_If](about_If.md)

[about_Operators](about_Operators.md)

[about_Quoting_Rules](about_Quoting_Rules.md)

[about_Script_Internationalization](about_Script_Internationalization.md)

[ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)

[Import-LocalizedData](xref:Microsoft.PowerShell.Utility.Import-LocalizedData)
