---
description: Descreve os diagramas de sintaxe usados no PowerShell.
keywords: powershell, cmdlet
ms.date: 06/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_command_syntax?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Command_Syntax
ms.openlocfilehash: a9da31213e76f5d28fbcb2cf4f4f6e9c49d51866
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196337"
---
# <a name="about-command-syntax"></a>Sobre a sintaxe do comando

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve os diagramas de sintaxe usados no PowerShell.

## <a name="long-description"></a>DESCRIÇÃO LONGA

Os cmdlets [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) e [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command) exibem diagramas de sintaxe para ajudá-lo a construir comandos corretamente. Este tópico explica como interpretar os diagramas de sintaxe.

## <a name="syntax-diagrams"></a>DIAGRAMAS DE SINTAXE

Cada parágrafo em um diagrama de sintaxe de comando representa uma forma válida do comando.

Para construir um comando, siga o diagrama de sintaxe da esquerda para a direita. Selecione entre os parâmetros opcionais e forneça valores para os espaços reservados.

O PowerShell usa a seguinte notação para diagramas de sintaxe.

```powershell
<command-name> -<Required Parameter Name> <Required Parameter Value>
[-<Optional Parameter Name> <Optional Parameter Value>]
[-<Optional Switch Parameters>]
[-<Optional Parameter Name>] <Required Parameter Value>
```

Veja a seguir a sintaxe do cmdlet [New-Alias](xref:Microsoft.PowerShell.Utility.New-Alias) .

```powershell
New-Alias [-Name] <string> [-Value] <string> [-Description <string>]
[-Force] [-Option {None | ReadOnly | Constant | Private | AllScope}]
[-PassThru] [-Scope <string>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

A sintaxe é capitalizada para facilitar a leitura, mas o PowerShell não diferencia maiúsculas de minúsculas.

O diagrama de sintaxe tem os elementos a seguir.

## <a name="command-name"></a>Nome de comando

Os comandos sempre começam com um nome de comando, como `New-Alias` . Digite o nome do comando ou seu alias, como "GCM" para `Get-Command` .

## <a name="parameters"></a>Parâmetros

Os parâmetros de um comando são opções que determinam o que o comando faz.
Alguns parâmetros usam um "valor" que é entrada do usuário para o comando.

Por exemplo, o `Get-Help` comando tem um parâmetro de **nome** que permite especificar o nome do tópico para o qual a ajuda é exibida. O nome do tópico é o valor do parâmetro **Name** .

Em um comando do PowerShell, os nomes de parâmetros sempre começam com um hífen.
O hífen informa ao PowerShell que o item no comando é um nome de parâmetro.

Por exemplo, para usar o parâmetro Name de `New-Alias` , digite o seguinte:

```powershell
-Name
```

Os parâmetros podem ser obrigatórios ou opcionais. Em um diagrama de sintaxe, os itens opcionais são colocados entre colchetes `[ ]` .

Para obter mais informações sobre parâmetros, consulte [about_Parameters](about_Parameters.md).

## <a name="parameter-values"></a>Valores dos parâmetros

Um valor de parâmetro é a entrada que o parâmetro pega. Como o Windows PowerShell se baseia na estrutura de Microsoft .NET, os valores de parâmetro são representados no diagrama de sintaxe por seu tipo .NET.

Por exemplo, o parâmetro Name de `Get-Help` usa um valor de "String", que é uma cadeia de caracteres de texto, como uma única palavra ou várias palavras entre aspas.

```powershell
[-Name] <string>
```

O tipo .NET de um valor de parâmetro é colocado entre colchetes angulares `< >` para indicar que ele é um espaço reservado para um valor e não um literal que você digita em um comando.

Para usar o parâmetro, substitua o espaço reservado do tipo .NET por um objeto que tenha o tipo .NET especificado.

Por exemplo, para usar o parâmetro **Name** , digite "-Name" seguido por uma cadeia de caracteres, como a seguinte:

```powershell
-Name MyAlias
```

## <a name="parameters-with-no-values"></a>Parâmetros sem valores

Alguns parâmetros não aceitam entrada, portanto, não têm um valor de parâmetro.
Parâmetros sem valores são chamados de "parâmetros de switch" porque eles funcionam como opções on/off. Você os inclui (ativado) ou os omite (desativado) de um comando.

Para usar um parâmetro de opção, basta digitar o nome do parâmetro, precedido por um hífen.

Por exemplo, para usar o parâmetro **WhatIf** do `New-Alias` cmdlet, digite o seguinte:

```powershell
-WhatIf
```

## <a name="parameter-sets"></a>Conjuntos de parâmetros

Os parâmetros de um comando são listados em conjuntos de parâmetros. Os conjuntos de parâmetros são semelhantes aos parágrafos de um diagrama de sintaxe.

O `New-Alias` cmdlet tem um conjunto de parâmetros, mas muitos cmdlets têm vários conjuntos de parâmetros. Alguns dos parâmetros de cmdlet são exclusivos para um conjunto de parâmetros e outros aparecem em vários conjuntos de parâmetros. Cada conjunto de parâmetros representa o formato de um comando válido. Um conjunto de parâmetros inclui apenas parâmetros que podem ser usados juntos em um comando. Se os parâmetros não puderem ser usados no mesmo comando, eles aparecerão em conjuntos de parâmetros separados.

Por exemplo, o cmdlet [Get-aleatório](xref:Microsoft.PowerShell.Utility.Get-Random) tem os seguintes conjuntos de parâmetros:

```powershell
Get-Random [[-Maximum] <Object>] [-Minimum <Object>] [-SetSeed <int>]
[<CommonParameters>]

Get-Random [-InputObject] <Object[]> [-Count <int>] [-SetSeed <int>]
[<CommonParameters>]
```

O primeiro conjunto de parâmetros, que retorna um número aleatório, tem os parâmetros **mínimo** e **máximo** . O segundo conjunto de parâmetros, que retorna um objeto selecionado aleatoriamente de um conjunto de objetos, inclui os parâmetros **InputObject** e **Count** . Ambos os conjuntos de parâmetros têm o parâmetro **setsemente** e os parâmetros comuns.

Esses conjuntos de parâmetros indicam que você pode usar os parâmetros **InputObject** e **Count** no mesmo comando, mas não pode usar os parâmetros **Maximum** e **Count** no mesmo comando.

Você indica qual conjunto de parâmetros deseja usar usando os parâmetros nesse conjunto de parâmetros.

No entanto, cada cmdlet também tem um conjunto de parâmetros padrão. O conjunto de parâmetros padrão é usado quando você não especifica parâmetros que são exclusivos para um conjunto de parâmetros. Por exemplo, se você usar `Get-Random` sem parâmetros, o Windows PowerShell pressupõe que você está usando o conjunto de parâmetros **Number** e retorna um número aleatório.

Em cada conjunto de parâmetros, os parâmetros aparecem na ordem de posição. A ordem dos parâmetros em um comando só é importante quando você omite os nomes de parâmetro opcionais. Quando os nomes de parâmetro são omitidos, o PowerShell atribui valores aos parâmetros por posição e tipo. Para obter mais informações sobre a posição do parâmetro, consulte `about_Parameters` .

## <a name="symbols-in-syntax-diagrams"></a>Símbolos em diagramas de sintaxe

O diagrama de sintaxe lista o nome do comando, os parâmetros de comando e os valores de parâmetro. Ele também usa símbolos para mostrar como construir um comando válido.

Os diagramas de sintaxe usam os seguintes símbolos:

- Um hífen `-` indica um nome de parâmetro. Em um comando, digite o hífen imediatamente antes do nome do parâmetro sem espaços intermediários, conforme mostrado no diagrama de sintaxe.

  Por exemplo, para usar o parâmetro **Name** de `New-Alias` , digite:

  ```powershell
  -Name
  ```

- Colchetes angulares `<>` indicam texto de espaço reservado. Você não digita os colchetes angulares ou o texto do espaço reservado em um comando. Em vez disso, substitua-o pelo item que ele descreve.

  Os colchetes angulares são usados para identificar o tipo .NET do valor que um parâmetro pega. Por exemplo, para usar o parâmetro **Name** do `New-Alias` cmdlet, você substitui o `<string>` por uma cadeia de caracteres, que é uma única palavra ou um grupo de palavras que são colocadas entre aspas.

- Os colchetes `[ ]` indicam itens opcionais. Um parâmetro e seu valor podem ser opcionais ou o nome de um parâmetro obrigatório pode ser opcional.

  Por exemplo, o parâmetro de **Descrição** de `New-Alias` e seu valor são colocados entre colchetes porque ambos são opcionais.

  ```powershell
  [-Description <string>]
  ```

  Os colchetes também indicam que o valor do parâmetro de nome `<string>` é necessário, mas o nome do parâmetro, "Name", é opcional.

  ```powershell
  [-Name] <string>
  ```

- Um colchete à direita e à esquerda `[]` anexado a um tipo .net indica que o parâmetro pode aceitar um ou vários valores desse tipo. Digite os valores em uma lista separada por vírgulas.

  Por exemplo, o parâmetro **Name** do `New-Alias` cmdlet usa apenas uma cadeia de caracteres, mas o parâmetro **Name** de [Get-Process](xref:Microsoft.PowerShell.Management.Get-Process) pode usar uma ou várias cadeias de caracteres.

  ```powershell
  New-Alias [-Name] <string>

  New-Alias -Name MyAlias
  ```

  ```powershell
  Get-Process [-Name] <string[]>

  Get-Process -Name Explorer, Winlogon, Services
  ```

- Chaves `{}` indicam uma "Enumeração", que é um conjunto de valores válidos para um parâmetro.

  Os valores nas chaves são separados por barras verticais `|` . Essas barras indicam uma opção "exclusiva ou", o que significa que você pode escolher apenas um valor do conjunto de valores que estão listados dentro das chaves.

  Por exemplo, a sintaxe para o `New-Alias` cmdlet inclui a seguinte enumeração de valor para o parâmetro de **opção** :

  ```powershell
  -Option {None | ReadOnly | Constant | Private | AllScope}
  ```

  As chaves e as barras verticais indicam que você pode escolher qualquer um dos valores listados para o parâmetro de **opção** , como "ReadOnly" ou "alscope".

  ```powershell
  -Option ReadOnly
  ```

## <a name="optional-items"></a>Itens opcionais

Os colchetes `[]` envolvem itens opcionais. Por exemplo, na `New-Alias` Descrição da sintaxe do cmdlet, o parâmetro de **escopo** é opcional. Isso é indicado na sintaxe pelos colchetes em volta do nome do parâmetro e do tipo:

```powershell
[-Scope <string>]
```

Ambos os exemplos a seguir são usos corretos do `New-Alias` cmdlet:

```powershell
New-Alias -Name utd -Value Update-TypeData
New-Alias -Name utd -Value Update-TypeData -Scope Global
```

Um nome de parâmetro pode ser opcional, mesmo se o valor para esse parâmetro for necessário. Isso é indicado na sintaxe pelos colchetes em volta do nome do parâmetro, mas não do tipo de parâmetro, como neste exemplo do `New-Alias` cmdlet:

```powershell
[-Name] <string> [-Value] <string>
```

Os comandos a seguir usam corretamente o `New-Alias` cmdlet. Os comandos produzem o mesmo resultado.

```powershell
New-Alias -Name utd -Value Update-TypeData
New-Alias -Name utd Update-TypeData
New-Alias utd -Value Update-TypeData
New-Alias utd Update-TypeData
```

Se o nome do parâmetro não estiver incluído na instrução como tipada, o Windows PowerShell tentará usar a posição dos argumentos para atribuir os valores aos parâmetros.

O exemplo a seguir não está completo:

```powershell
New-Alias utd
```

Esse cmdlet requer valores para os parâmetros **Name** e **Value** .

Em exemplos de sintaxe, os colchetes também são usados na nomeação e na conversão para tipos de .NET Framework. Nesse contexto, os colchetes não indicam que um elemento é opcional.

## <a name="see-also"></a>CONSULTE TAMBÉM

- [about_Parameters](about_Parameters.md)
- [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command)
- [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help)

