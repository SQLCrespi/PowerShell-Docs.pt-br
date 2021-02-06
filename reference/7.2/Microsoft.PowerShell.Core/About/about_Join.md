---
description: Descreve como o operador de junção (-join) combina várias cadeias de caracteres em uma única cadeia.
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_join?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Join
ms.openlocfilehash: d76e95aaeca1b5b94bb1a2216576a985ffb209c0
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597599"
---
# <a name="about-join"></a>Sobre a junção

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve como o operador de junção (-join) combina várias cadeias de caracteres em uma única cadeia.

## <a name="long-description"></a>DESCRIÇÃO LONGA

O operador Join concatena um conjunto de cadeias de caracteres em uma única cadeia. As cadeias são anexadas à cadeia de caracteres resultante na ordem em que aparecem no comando.

### <a name="syntax"></a>Syntax

O diagrama a seguir mostra a sintaxe para o operador join.

```powershell
-Join <String[]>
<String[]> -Join <Delimiter>
```

#### <a name="parameters"></a>Parâmetros

String [] – Especifica uma ou mais cadeias de caracteres a serem unidas.

Delimitador-especifica um ou mais caracteres colocados entre as cadeias concatenadas. O padrão é nenhum delimitador ("").

Comentários

O operador de junção unário (-Join <String [] >) tem precedência maior do que uma vírgula. Como resultado, se você enviar uma lista separada por vírgulas de cadeias de caracteres para o operador unário, somente a primeira cadeia de caracteres (antes da primeira vírgula) será enviada ao operador join.

Para usar o operador unário Join, coloque as cadeias de caracteres entre parênteses ou armazene as cadeias de caracteres em uma variável e, em seguida, envie a variável para join.

Por exemplo:

```powershell
-join "a", "b", "c"
a
b
c

-join ("a", "b", "c")
abc

$z = "a", "b", "c"
-join $z
abc
```

### <a name="examples"></a>Exemplos

A instrução a seguir une três cadeias de caracteres:

```powershell
-join ("Windows", "PowerShell", "2.0")
WindowsPowerShell2.0
```

A instrução a seguir une três cadeias de caracteres delimitadas por um espaço:

```powershell
"Windows", "PowerShell", "2.0" -join " "
Windows PowerShell 2.0
```

As instruções a seguir usam um delimitador de vários caracteres para unir três cadeias:

```powershell
$a = "WIND", "S P", "ERSHELL"
$a -join "OW"
WINDOWS POWERSHELL
```

A instrução a seguir une as linhas em uma cadeia de caracteres here em uma única cadeia de caracteres. Como uma cadeia de caracteres here é uma cadeia de caracteres, as linhas na cadeia de caracteres here devem ser divididas antes que possam ser Unidas. Você pode usar esse método para reassociar as cadeias de caracteres em um arquivo XML que foi salvo em uma cadeia de caracteres aqui:

```powershell
$a = @'
a
b
c
'@

(-split $a) -join " "
a b c
```

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Operators](about_Operators.md)

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Split](about_Split.md)

