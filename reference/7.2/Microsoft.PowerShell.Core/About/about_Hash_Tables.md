---
description: Descreve como criar, usar e classificar tabelas de hash no PowerShell.
Locale: en-US
ms.date: 11/28/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_hash_tables?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Hash_Tables
ms.openlocfilehash: dec2683acfa4fcf79419beea9e0840387d3d43d1
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596165"
---
# <a name="about-hash-tables"></a>Sobre tabelas de hash

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve como criar, usar e classificar tabelas de hash no PowerShell.

## <a name="long-description"></a>DESCRIÇÃO LONGA

Uma tabela de hash, também conhecida como um dicionário ou uma matriz associativa, é uma estrutura de dados compacta que armazena um ou mais pares chave/valor. Por exemplo, uma tabela de hash pode conter uma série de endereços IP e nomes de computador, onde os endereços IP são as chaves e os nomes dos computadores são os valores, ou vice-versa.

No PowerShell, cada tabela de hash é um objeto Hashtable (System. Collections. Hashtable). Você pode usar as propriedades e métodos de objetos de tabela de hash no PowerShell.

A partir do PowerShell 3,0, você pode usar o atributo [ordenado] para criar um dicionário ordenado (System. Collections. especializada. OrderedDictionary) no PowerShell.

Os dicionários ordenados diferem das tabelas de hash, pois as chaves sempre aparecem na ordem em que são listadas. A ordem das chaves em uma tabela de hash não é determinada.

As chaves e o valor em tabelas de hash também são objetos .NET. Eles são geralmente cadeias de caracteres ou inteiros, mas podem ter qualquer tipo de objeto. Você também pode criar tabelas de hash aninhadas, nas quais o valor de uma chave é outra tabela de hash.

As tabelas de hash são frequentemente usadas porque são muito eficientes para localizar e recuperar dados. Você pode usar tabelas de hash para armazenar listas e criar propriedades calculadas no PowerShell. E o PowerShell tem um cmdlet, ConvertFrom-StringData, que converte cadeias de caracteres em uma tabela de hash.

### <a name="syntax"></a>Syntax

A sintaxe de uma tabela de hash é a seguinte:

```powershell
@{ <name> = <value>; [<name> = <value> ] ...}
```

A sintaxe de um dicionário ordenado é a seguinte:

```powershell
[ordered]@{ <name> = <value>; [<name> = <value> ] ...}
```

O atributo [ordered] foi introduzido no PowerShell 3,0.

### <a name="creating-hash-tables"></a>Criando tabelas de hash

Para criar uma tabela de hash, siga estas diretrizes:

- Inicie a tabela de hash com um sinal de arroba (@).
- Coloque a tabela de hash entre chaves ( {} ).
- Insira um ou mais pares de chave/valor para o conteúdo da tabela de hash.
- Use um sinal de igual (=) para separar cada chave de seu valor.
- Use um ponto e vírgula (;) ou uma quebra de linha para separar os pares de chave/valor.
- A chave que contém espaços deve ser colocada entre aspas. Os valores devem ser expressões válidas do PowerShell. As cadeias de caracteres devem aparecer entre aspas, mesmo que não incluam espaços.
- Para gerenciar a tabela de hash, salve-a em uma variável.
- Ao atribuir uma tabela de hash ordenada a uma variável, coloque o atributo [ordenado] antes do símbolo "@". Se você o posicionar antes do nome da variável, o comando falhará.

Para criar uma tabela de hash vazia no valor de $hash, digite:

```powershell
$hash = @{}
```

Você também pode adicionar chaves e valores a uma tabela de hash ao criá-la. Por exemplo, a instrução a seguir cria uma tabela de hash com três chaves.

```powershell
$hash = @{ Number = 1; Shape = "Square"; Color = "Blue"}
```

### <a name="creating-ordered-dictionaries"></a>Criando dicionários ordenados

Você pode criar um dicionário ordenado adicionando um objeto do tipo OrderedDictionary, mas a maneira mais fácil de criar um dicionário ordenado é usar o atributo [ordered].

O atributo [ordered] é introduzido no PowerShell 3,0.

Coloque o atributo imediatamente antes do símbolo "@".

```powershell
$hash = [ordered]@{ Number = 1; Shape = "Square"; Color = "Blue"}
```

Você pode usar dicionários ordenados da mesma maneira que usa tabelas de hash.
Qualquer um dos tipos pode ser usado como o valor dos parâmetros que usam uma tabela de hash ou um dicionário (iDictionary).

Você não pode usar o atributo [ordenado] para converter ou transmitir uma tabela de hash. Se você posicionar o atributo ordenado antes do nome da variável, o comando falhará com a seguinte mensagem de erro.

```powershell
PS C:\> [ordered]$hash = @{}
At line:1 char:1
+ [ordered]$hash = @{}
+ [!INCLUDE[]()]
The ordered attribute can be specified only on a hash literal node.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordExc
eption
+ FullyQualifiedErrorId : OrderedAttributeOnlyOnHashLiteralNode
```

Para corrigir a expressão, mova o atributo [ordenado].

```powershell
PS C:\> $hash = [ordered]@{}
```

Você pode converter um dicionário ordenado em uma tabela de hash, mas não pode recuperar o atributo ordenado, mesmo se você limpar a variável e inserir novos valores. Para restabelecer o pedido, você deve remover e recriar a variável.

```
PS C:\> [hashtable]$hash = [ordered]@{
>> Number = 1; Shape = "Square"; Color = "Blue"}
PS C:\> $hash

Name                           Value
----                           -----
Color                          Blue
Shape                          Square
Number                         1
```

### <a name="displaying-hash-tables"></a>Exibindo tabelas de hash

Para exibir uma tabela de hash que é salva em uma variável, digite o nome da variável.
Por padrão, as tabelas de hash são exibidas como uma tabela com uma coluna para chaves e outra para valores.

```powershell
C:\PS> $hash

Name                           Value
----                           -----
Shape                          Square
Color                          Blue
Number                         1
```

As tabelas de hash têm propriedades de chaves e valores. Use a notação de ponto para exibir todas as chaves ou todos os valores.

```powershell
C:\PS> $hash.keys
Number
Shape
Color

C:\PS> $hash.values
1
Square
Blue
```

Cada nome de chave também é uma propriedade da tabela de hash e seu valor é o valor da propriedade Key-Name. Use o formato a seguir para exibir os valores de propriedade.

```powershell
$hashtable.<key>
<value>
```

Por exemplo:

```powershell
C:\PS> $hash.Number
1

C:\PS> $hash.Color
Blue
```

Se o nome da chave colidir com um dos nomes de Propriedade do tipo de tabela de hash, você poderá usar `PSBase` para acessar essas propriedades. Por exemplo, se o nome da chave for `keys` e você quiser retornar a coleção de chaves, use esta sintaxe:

```powershell
$hashtable.PSBase.Keys
```

As tabelas de hash têm uma propriedade Count que indica o número de pares chave-valor na tabela de hash.

```powershell
C:\PS> $hash.count
3
```

As tabelas de tabela de hash não são matrizes, portanto, você não pode usar um inteiro como um índice na tabela de hash, mas pode usar um nome de chave para indexar a tabela de hash.
Se a chave for um valor de cadeia de caracteres, coloque o nome da chave entre aspas.

Por exemplo:

```powershell
C:\PS> $hash["Number"]
1
```

### <a name="adding-and-removing-keys-and-values"></a>Adicionando e removendo chaves e valores

Para adicionar chaves e valores a uma tabela de hash, use o seguinte formato de comando.

```powershell
$hash["<key>"] = "<value>"
```

Por exemplo, para adicionar uma chave "Time" com um valor de "Now" à tabela de hash, use o formato de instrução a seguir.

```powershell
$hash["Time"] = "Now"
```

Você também pode adicionar chaves e valores a uma tabela de hash usando o método Add do objeto System. Collections. Hashtable. O método Add tem a seguinte sintaxe:

```powershell
Add(Key, Value)
```

Por exemplo, para adicionar uma chave "Time" com um valor de "Now" à tabela de hash, use o formato de instrução a seguir.

```powershell
$hash.Add("Time", "Now")
```

Além disso, você pode adicionar chaves e valores a uma tabela de hash usando o operador de adição (+) para adicionar uma tabela de hash a uma tabela de hash existente. Por exemplo, a instrução a seguir adiciona uma chave "Time" com um valor de "Now" à tabela de hash na variável $hash.

```powershell
$hash = $hash + @{Time="Now"}
```

Você também pode adicionar valores que são armazenados em variáveis.

```powershell
$t = "Today"
$now = (Get-Date)

$hash.Add($t, $now)
```

Não é possível usar um operador de subtração para remover um par de chave/valor de uma tabela de hash, mas você pode usar o método remove do objeto Hashtable. O método remove usa a chave como seu valor.

O método remove tem a seguinte sintaxe:

```
Remove(Key)
```

Por exemplo, para remover o par de chave/valor time = Now da tabela de hash no valor da variável $hash, digite:

```powershell
$hash.Remove("Time")
```

Você pode usar todas as propriedades e métodos de objetos de tabela de hash no PowerShell, incluindo contém, Clear, clone e CopyTo. Para obter mais informações sobre objetos de tabela de hash, consulte [System. Collections. Hashtable](/dotnet/api/system.collections.hashtable).

### <a name="object-types-in-hashtables"></a>Tipos de objeto em HashTables

As chaves e os valores em uma tabela de hash podem ter qualquer tipo de objeto .NET, e uma única tabela de hash pode ter chaves e valores de vários tipos.

A instrução a seguir cria uma tabela de hash de cadeias de caracteres de nome do processo e valores de objeto de processo e salva-o na `$p` variável.

```powershell
$p = @{"PowerShell" = (Get-Process PowerShell);
"Notepad" = (Get-Process notepad)}
```

Você pode exibir a tabela de hash no `$p` e usar as propriedades de nome de chave para exibir os valores.

```powershell
C:\PS> $p

Name                           Value
----                           -----
PowerShell                     System.Diagnostics.Process (PowerShell)
Notepad                        System.Diagnostics.Process (notepad)

C:\PS> $p.PowerShell

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    441      24    54196      54012   571     5.10   1788 PowerShell

C:\PS> $p.keys | foreach {$p.$_.handles}
441
251
```

As chaves em uma tabela de hash também podem ser de qualquer tipo .NET. A instrução a seguir adiciona um par chave/valor à tabela de hash na `$p` variável. A chave é um objeto de serviço que representa o serviço WinRM e o valor é o status atual do serviço.

```powershell
C:\PS> $p = $p + @{(Get-Service WinRM) = ((Get-Service WinRM).Status)}
```

Você pode exibir e acessar o novo par chave/valor usando os mesmos métodos que você usa para outros pares na tabela de hash.

```powershell
C:\PS> $p

Name                           Value
----                           -----
PowerShell                     System.Diagnostics.Process (PowerShell)
Notepad                        System.Diagnostics.Process (notepad)
System.ServiceProcess.Servi... Running

C:\PS> $p.keys
PowerShell
Notepad

Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...

C:\PS> $p.keys | foreach {$_.name}
winrm
```

As chaves e os valores em uma tabela de hash também podem ser objetos de Hashtable. A instrução a seguir adiciona o par chave/valor à tabela de hash na `$p` variável em que a chave é uma cadeia de caracteres, Hash2, e o valor é uma tabela de hash com três pares de chave/valor.

```powershell
C:\PS> $p = $p + @{"Hash2"= @{a=1; b=2; c=3}}
```

Você pode exibir e acessar os novos valores usando os mesmos métodos.

```powershell
C:\PS> $p

Name                           Value
----                           -----
PowerShell                     System.Diagnostics.Process (PowerShell)
Notepad                        System.Diagnostics.Process (notepad)
System.ServiceProcess.Servi... Running
Hash2                          {a, b, c}

C:\PS> $p.Hash2

Name                           Value
----                           -----
a                              1
b                              2
c                              3

C:\PS> $p.Hash2.b
2
```

### <a name="sorting-keys-and-values"></a>Classificando chaves e valores

Os itens em uma tabela de hash são intrinsecamente desordenados. Os pares de chave/valor podem aparecer em uma ordem diferente cada vez que você os exibir.

Embora não seja possível classificar uma tabela de hash, você pode usar o método GetEnumerator de tabelas de hash para enumerar as chaves e os valores e, em seguida, usar o cmdlet Sort-Object para classificar os valores enumerados para exibição.

Por exemplo, os comandos a seguir enumeram as chaves e os valores na tabela de hash na `$p` variável e, em seguida, classificam as chaves em ordem alfabética.

```powershell
C:\PS> $p.GetEnumerator() | Sort-Object -Property key

Name                           Value
----                           -----
Notepad                        System.Diagnostics.Process (notepad)
PowerShell                     System.Diagnostics.Process (PowerShell)
System.ServiceProcess.Servi... Running
```

O comando a seguir usa o mesmo procedimento para classificar os valores de hash em ordem decrescente.

```powershell
C:\PS> $p.getenumerator() | Sort-Object -Property Value -Descending

Name                           Value
----                           -----
PowerShell                     System.Diagnostics.Process (PowerShell)
Notepad                        System.Diagnostics.Process (notepad)
System.ServiceProcess.Servi... Running
```

### <a name="creating-objects-from-hash-tables"></a>Criando objetos a partir de tabelas de hash

A partir do PowerShell 3,0, você pode criar um objeto de uma tabela de hash de propriedades e valores de propriedade.

A sintaxe dela é a seguinte:

```powershell
[<class-name>]@{
  <property-name>=<property-value>
  <property-name>=<property-value>
}
```

Esse método funciona somente para classes que têm um Construtor nulo, ou seja, um construtor que não tem parâmetros. As propriedades do objeto devem ser públicas e configurável.

Para obter mais informações, consulte [about_Object_Creation](about_Object_Creation.md).

### <a name="convertfrom-stringdata"></a>ConvertFrom-StringData

O `ConvertFrom-StringData` cmdlet converte uma cadeia de caracteres ou uma cadeia de caracteres here de pares de chave/valor em uma tabela de hash. Você pode usar o `ConvertFrom-StringData` cmdlet com segurança na seção de dados de um script e pode usá-lo com o `Import-LocalizedData` cmdlet para exibir mensagens de usuário na cultura da interface do usuário do usuário atual.

Aqui-as cadeias de caracteres são especialmente úteis quando os valores na tabela de hash incluem aspas. Para obter mais informações sobre as cadeias de caracteres aqui, consulte [about_Quoting_Rules](about_Quoting_Rules.md).

O exemplo a seguir mostra como criar uma cadeia de caracteres here das mensagens de usuário no exemplo anterior e como usar `ConvertFrom-StringData` para convertê-las de uma cadeia de caracteres em uma tabela de hash.

O comando a seguir cria uma cadeia de caracteres here dos pares de chave/valor e, em seguida, salva-o na \$ variável de cadeia de caracteres.

```powershell
C:\PS> $string = @"
Msg1 = Type "Windows".
Msg2 = She said, "Hello, World."
Msg3 = Enter an alias (or "nickname").
"@
```

Esse comando usa o cmdlet ConvertFrom-StringData para converter a cadeia de caracteres here em uma tabela de hash.

```powershell
C:\PS> ConvertFrom-StringData $string

Name                           Value
----                           -----
Msg3                           Enter an alias (or "nickname").
Msg2                           She said, "Hello, World."
Msg1                           Type "Windows".
```

Para obter mais informações sobre as cadeias de caracteres aqui, consulte [about_Quoting_Rules](about_Quoting_Rules.md).

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Arrays](about_Arrays.md)

[about_Object_Creation](about_Object_Creation.md)

[about_Quoting_Rules](about_Quoting_Rules.md)

[about_Script_Internationalization](about_Script_Internationalization.md)

[ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)

[Import-LocalizedData](xref:Microsoft.PowerShell.Utility.Import-LocalizedData)

[System.Collections.Hashtable](/dotnet/api/system.collections.hashtable)
