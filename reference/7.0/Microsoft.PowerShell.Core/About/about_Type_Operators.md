---
description: Descreve os operadores que funcionam com tipos de Microsoft .NET.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/15/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_type_operators?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Type_Operators
ms.openlocfilehash: 807b99175463b930177f293eaf6c2fd8cc5bc224
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "93196444"
---
# <a name="about-type-operators"></a>Sobre operadores de tipo

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve os operadores que funcionam com tipos de Microsoft .NET.

## <a name="long-description"></a>DESCRIÇÃO LONGA

Os operadores de tipo booliano ( `-is` e `-isNot` ) informam se um objeto é uma instância de um tipo .net especificado. O `-is` operador retornará um valor **true** se o tipo corresponder e um valor de **false** , caso contrário. O `-isNot` operador retornará um valor **false** se o tipo corresponder e um valor de **verdadeiro** caso contrário.

O `-as` operador tenta converter o objeto de entrada para o tipo .net especificado. Se tiver sucesso, ele retornará o objeto convertido. Se falhar, ele retornará `$null` . Ele não retorna um erro.

A tabela a seguir lista os operadores de tipo no PowerShell.

|Operador|Descrição                |Exemplo                          |
|--------|---------------------------|---------------------------------|
|`-is`   |Retorna TRUE quando a entrada|`(get-date) -is [DateTime]`      |
|        |é uma instância do      |`True`                           |
|        |tipo .NET especificado.       |                                 |
|`-isNot`|Retorna TRUE quando a entrada|`(get-date) -isNot [DateTime]`   |
|        |Não é uma instância do     |`False`                          |
|        |tipo de specified.NET.        |                                 |
|`-as`   |Converte a entrada para o  |`"5/7/07" -as [DateTime]`        |
|        |tipo .NET especificado.       |`Monday, May 7, 2007 12:00:00 AM`|

A sintaxe dos operadores de tipo é a seguinte:

```powershell
<input> <operator> [.NET type]
```

Você também pode usar a seguinte sintaxe:

```powershell
<input> <operator> ".NET type"
```

O tipo .NET pode ser escrito como um nome de tipo entre colchetes ou uma cadeia de caracteres, como `[DateTime]` ou `"DateTime"` para **System. DateTime** . Se o tipo não estiver na raiz do namespace do sistema, especifique o nome completo do tipo de objeto. Você pode omitir "System.". Por exemplo, para especificar **System. Diagnostics. Process** , digite `[System.Diagnostics.Process]` , `[Diagnostics.Process]` ou `"Diagnostics.Process"` .

Os operadores de tipo sempre operam no objeto de entrada como um todo. Ou seja, se o objeto de entrada for uma coleção, ele será o tipo de _coleção_ que é testado, não os tipos dos _elementos_ da coleção.

### <a name="-isisnot-operators"></a>-operadores is/isNot

Os operadores de tipo **booliano** ( `-is` e `-isNot` ) sempre retornam um valor **booliano** , mesmo que a entrada seja uma coleção de objetos.

Se `<input>` é um tipo que é igual a ou é _derivado_ do tipo .net, o `-is` operador retorna `$True` .

Por exemplo, o tipo **DirectoryInfo** é derivado do tipo **FileSystemInfo** . Portanto, ambos os exemplos retornam **true** .

```powershell
PS> (Get-Item /) -is [System.IO.DirectoryInfo]
True
PS> (Get-Item /) -is [System.IO.FileSystemInfo]
True
```

O `-is` operador também pode corresponder a interfaces se o `<input>` implementar a interface na comparação. Neste exemplo, a entrada é uma matriz. As matrizes implementam a interface **System. Collections. IList** .

```powershell
PS> 1, 2 -is [System.Collections.IList]
True
```

### <a name="-as-operator"></a>operador-as

O `-as` operador tenta converter o objeto de entrada para o tipo .net especificado. Se tiver sucesso, ele retornará o objeto convertido. Se falhar, ele retornará `$null` . Ele não retorna um erro.

Se o `<input>` for um tipo que é _derivado_ do tipo .NET `-as` _passa por_ retornar objeto de entrada inalterado. Por exemplo, o tipo **DirectoryInfo** é derivado do tipo **FileSystemInfo** . Portanto, o tipo de objeto não é alterado no exemplo a seguir:

```powershell
PS> $fsroot = (Get-Item /) -as [System.IO.FileSystemInfo]
PS> $fsroot.GetType().FullName
System.IO.DirectoryInfo
```

#### <a name="converting-the-datetime-type-is-culture-sensitive"></a>Converter o tipo DateTime é sensível à cultura

Diferentemente da conversão de tipo, a conversão para `[DateTime]` o tipo usando o `-as` operador só funciona com cadeias de caracteres formatadas de acordo com as regras da cultura atual.

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr-FR'
PS> '13/5/20' -as [datetime]

mercredi 13 mai 2020 00:00:00

PS> '05/13/20' -as [datetime]
PS> [datetime]'05/13/20'

mercredi 13 mai 2020 00:00:00

PS> [datetime]'13/05/20'
InvalidArgument: Cannot convert value "13/05/20" to type "System.DateTime".
Error: "String '13/05/20' was not recognized as a valid DateTime."
```

Para localizar o tipo .NET de um objeto, use o `Get-Member` cmdlet. Ou use o método **GetType** de todos os objetos junto com a propriedade **FullName** desse método. Por exemplo, a instrução a seguir obtém o tipo de valor de retorno de um `Get-Culture` comando:

```powershell
PS> (Get-Culture).GetType().FullName
System.Globalization.CultureInfo
```

## <a name="examples"></a>EXEMPLOS

Os exemplos a seguir mostram alguns usos dos operadores de tipo:

```powershell
PS> 32 -is [Float]
False

PS> 32 -is "int"
True

PS> (get-date) -is [DateTime]
True

PS> "12/31/2007" -is [DateTime]
False

PS> "12/31/2007" -is [String]
True

PS> (get-process PowerShell)[0] -is [System.Diagnostics.Process]
True

PS> (get-command get-member) -is [System.Management.Automation.CmdletInfo]
True
```

O exemplo a seguir mostra que quando a entrada é uma coleção de objetos, o tipo de correspondência é o tipo .NET da coleção, não o tipo dos objetos individuais na coleção.

Neste exemplo, embora os `Get-Culture` `Get-UICulture` cmdlets e retornem objetos **System. Globalization. CultureInfo** , uma coleção desses objetos é uma matriz System. Object.

```powershell
PS> (get-culture) -is [System.Globalization.CultureInfo]
True

PS> (get-uiculture) -is [System.Globalization.CultureInfo]
True

PS> (get-culture), (get-uiculture) -is [System.Globalization.CultureInfo]
False

PS> (get-culture), (get-uiculture) -is [Array]
True

PS> (get-culture), (get-uiculture) | foreach {
  $_ -is [System.Globalization.CultureInfo])
}
True
True

PS> (get-culture), (get-uiculture) -is [Object]
True
```

Os exemplos a seguir mostram como usar o `-as` operador.

```powershell
PS> "12/31/07" -is [DateTime]
False

PS> "12/31/07" -as [DateTime]
Monday, December 31, 2007 12:00:00 AM

PS> $date = "12/31/07" -as [DateTime]

C:\PS>$a -is [DateTime]
True

PS> 1031 -as [System.Globalization.CultureInfo]

LCID      Name      DisplayName
----      ----      -----------
1031      de-DE     German (Germany)
```

O exemplo a seguir mostra que quando o `-as` operador não pode converter o objeto de entrada para o tipo .net, ele retorna `$null` .

```powershell
PS> 1031 -as [System.Diagnostics.Process]
PS>
```

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Operators](about_Operators.md)
