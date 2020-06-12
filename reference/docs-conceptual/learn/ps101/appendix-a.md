---
title: Appendix A - Help Syntax (Apêndice A – Sintaxe de Ajuda)
description: Este artigo explica como ler e entender a sintaxe de um cmdlet, conforme apresentado por Get-Help.
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: e8e28f66c02370b098f63a0396ef8a724cf3a1bd
ms.sourcegitcommit: 0d958eac5bde5ccf5ee2c1bac4f009a63bf71368
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2020
ms.locfileid: "84437977"
---
# <a name="appendix-a---help-syntax"></a>Appendix A - Help Syntax (Apêndice A – Sintaxe de Ajuda)

O exemplo a seguir mostra a seção **SINTAXE** da Ajuda para o cmdlet `Get-EventLog`.

```powershell
help Get-EventLog
```

```Output
NAME
    Get-EventLog

SYNOPSIS
    Gets the events in an event log, or a list of the event logs, on the local or remote
    computers.


SYNTAX
    Get-EventLog [-LogName] <String> [[-InstanceId] <Int64[]>] [-After <DateTime>]
    [-AsBaseObject] [-Before <DateTime>] [-ComputerName <String[]>] [-EntryType {Error |
    Information | FailureAudit | SuccessAudit | Warning}] [-Index <Int32[]>] [-Message
    <String>] [-Newest <Int32>] [-Source <String[]>] [-UserName <String[]>]
    [<CommonParameters>]

    Get-EventLog [-AsString] [-ComputerName <String[]>] [-List] [<CommonParameters>]
```

Somente a parte relevante da Ajuda é mostrada neste exemplo.

A sintaxe é composta principalmente por vários conjuntos de colchetes de abertura e fechamento (`[]`). Eles têm dois significados diferentes, dependendo de como são usados. Qualquer coisa contida dentro de colchetes é opcional, a menos que eles sejam um conjunto de colchetes vazios `[]`. Colchetes vazios só aparecem após um tipo de dados, como `<string[]>`. Isso significa que o parâmetro específico pode aceitar mais de um valor desse tipo.

O primeiro parâmetro no primeiro conjunto de parâmetros de `Get-EventLog` é **LogName**. LogName está entre colchetes, o que significa que é um parâmetro posicional. Em outras palavras, a especificação do nome do parâmetro em si é opcional, desde que ele seja especificado na posição correta. As informações contidas nos colchetes angulares (`<>`) após o nome do parâmetro indicam que ele precisa de um só valor de **cadeia de caracteres**. O nome do parâmetro inteiro e o tipo de dados não são incluídos entre colchetes e, portanto, o parâmetro **LogName** é necessário ao usar esse conjunto de parâmetros.

```powershell
Get-EventLog [-LogName] <String>
```

O segundo parâmetro é **InstanceId**. Observe que o nome do parâmetro e o tipo de dados são colocados por completo entre colchetes. Isso significa que o parâmetro **InstanceId** é opcional, não obrigatório. Observe também que **InstanceId** é colocada entre um conjunto de colchetes próprio. Assim como ocorre com o parâmetro **LogName**, isso significa que o parâmetro é posicional. Há um último conjunto de colchetes após o tipo de dados. Isso significa que ele pode aceitar mais de um valor na forma de uma matriz ou uma lista separada por vírgula.

```
[[-InstanceId] <Int64[]>]
```

O segundo conjunto de parâmetros tem um parâmetro **List**. É um parâmetro de opção, porque não há nenhum tipo de dados após o nome do parâmetro. Quando o parâmetro **List** é especificado, o valor é **True**. Quando ele não for especificado, o valor é **False**.

```
[-List]
```

As informações de sintaxe de um comando também podem ser recuperadas usando `Get-Command` por meio do parâmetro **Syntax**. Esse é um atalho útil que uso o tempo todo. Ele me permite aprender rapidamente a usar um comando sem precisar percorrer várias páginas de informações da Ajuda. Se eu acabar precisando de mais informações, voltarei a usar o conteúdo real da Ajuda.

```powershell
Get-Command -Name Get-EventLog -Syntax
```

```Output
Get-EventLog [-LogName] <string> [[-InstanceId] <long[]>] [-ComputerName <string[]>] [-Newest <int>]
 [-After <datetime>] [-Before <datetime>] [-UserName <string[]>] [-Index <int[]> ]
 [-EntryType <string[]>] [-Source <string[]>] [-Message <string>] [-AsBaseObject]
 [<CommonParameters>]

Get-EventLog [-ComputerName <string[]>] [-List] [-AsString] [<CommonParameters>]
```

Quanto mais você usar o sistema de Ajuda do PowerShell, mais fácil será memorizar todas as diferentes nuances. Antes que você se dê conta, o uso dele passará a ser algo natural.
