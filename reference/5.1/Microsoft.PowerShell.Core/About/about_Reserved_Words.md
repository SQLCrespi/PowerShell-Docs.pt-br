---
description: Lista as palavras reservadas que não podem ser usadas como identificadores porque elas têm um significado especial no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_reserved_words?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Reserved_Words
ms.openlocfilehash: 99b56e433ccb39ba0f199068086bcdaddf36590e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195977"
---
# <a name="about-reserved-words"></a>Sobre palavras reservadas

## <a name="short-description"></a>DESCRIÇÃO BREVE
Lista as palavras reservadas que não podem ser usadas como identificadores porque elas têm um significado especial no PowerShell.

## <a name="long-description"></a>DESCRIÇÃO LONGA

Há certas palavras que têm significado especial no PowerShell. Quando essas palavras aparecem sem aspas, o PowerShell tenta aplicar seu significado especial em vez de tratá-las como cadeias de caracteres. Para usar essas palavras como argumentos de parâmetro em um comando ou script sem invocar seu significado especial, coloque as palavras reservadas entre aspas.

A seguir estão as palavras reservadas no PowerShell:

```
assembly         exit            process
base             filter          public
begin            finally         return
break            for             sequence
catch            foreach         static
class            from (*)        switch
command          function        throw
configuration    hidden          trap
continue         if              try
data             in              type
define (*)       inlinescript    until
do               interface       using
dynamicparam     module          var (*)
else             namespace       while
elseif           parallel        workflow
end              param
enum             private

(*) These keywords are reserved for future use.
```

Várias palavras-chave de linguagem, incluindo `Foreach` ,, `If` `For` e `While` , têm seus próprios artigos de ajuda. Para exibi-los, digite `Get-Help about_` e adicione a palavra-chave. Por exemplo, para obter informações sobre a `Foreach` instrução, digite:

```powershell
Get-Help about_ForEach
```

Para obter informações sobre a `Filter` instrução ou a `Return` sintaxe da instrução, digite:

```powershell
Get-Help about_Functions
```

Para obter informações sobre outras palavras reservadas, digite:

```powershell
Get-Help <Reserved_Word>
```

> [!NOTE]
> Nem todas as palavras reservadas têm seu próprio artigo de ajuda. Se o `Get-Help` não retornar um artigo, você poderá procurar artigos que falam sobre a palavra reservada usando o seguinte comando:
>
> ```powershell
> Get-Help <Reserved_Word> -Category:HelpFile
> ```

## <a name="see-also"></a>CONSULTE TAMBÉM

- [about_Command_Syntax](about_Command_Syntax.md)
- [about_Language_Keywords](about_Language_Keywords.md)
- [about_Parsing](about_Parsing.md)
- [about_Quoting_Rules](about_Quoting_Rules.md)
- [about_Script_Blocks](about_Script_Blocks.md)
- [about_Special_Characters](about_Special_Characters.md)
