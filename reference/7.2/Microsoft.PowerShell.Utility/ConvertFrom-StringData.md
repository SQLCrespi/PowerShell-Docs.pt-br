---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/21/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-stringdata?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-StringData
ms.openlocfilehash: c95ebca6307d58668c31faf3e492617f49ddebf4
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599037"
---
# ConvertFrom-StringData

## SINOPSE
Converte uma cadeia de caracteres que contém um ou mais pares de chave/valor em uma tabela de hash.

## SYNTAX

### Tudo

```
ConvertFrom-StringData [-StringData] <String> [[-Delimiter] <Char>] [<CommonParameters>]
```

## DESCRIPTION

O `ConvertFrom-StringData` cmdlet converte uma cadeia de caracteres que contém um ou mais pares de chave e valor em uma tabela de hash. Como cada par chave-valor deve estar em uma linha separada, as cadeias de caracteres aqui são geralmente usadas como o formato de entrada. Por padrão, a **chave** deve ser separada do **valor** por um caractere de sinal de igual ( `=` ).

O `ConvertFrom-StringData` cmdlet é considerado um cmdlet seguro que pode ser usado na `DATA` seção de um script ou função. Quando usado em uma `DATA` seção, o conteúdo da cadeia de caracteres deve estar de acordo com as regras para uma seção de dados. Para obter mais informações, consulte [about_Data_Sections](../Microsoft.PowerShell.Core/About/about_Data_Sections.md).

`ConvertFrom-StringData` dá suporte a sequências de caracteres de escape que são permitidas pelas ferramentas convencionais de tradução automática. Ou seja, o cmdlet pode interpretar barras invertidas ( `\` ) como caracteres de escape nos dados da cadeia de caracteres usando o [método Regex. Unescape](/dotnet/api/system.text.regularexpressions.regex.unescape), em vez do caractere de barra () do PowerShell \` que normalmente sinalizaria o final de uma linha em um script. Dentro da cadeia de caracteres here, o caractere de acento grave não funciona. Você também pode preservar uma barra invertida literal em seus resultados, recortando-a com uma barra invertida precedente, desta forma: `\\` . Caracteres de barra invertida sem escape, como aqueles que geralmente são usados em caminhos de arquivo, podem ser processados como sequências de escape ilegais em seus resultados.

O PowerShell 7 adiciona o parâmetro **delimitador** .

## EXEMPLOS

### Exemplo 1: converter uma cadeia de caracteres here entre aspas simples em uma tabela de hash

Este exemplo converte uma cadeia de caracteres aqui entre aspas simples de mensagens de usuário em uma tabela de hash. Em uma cadeia de caracteres entre aspas simples, os valores não são substituídos por variáveis e as expressões não são avaliadas.
O `ConvertFrom-StringData` cmdlet converte o valor na `$Here` variável em uma tabela de hash.

```powershell
$Here = @'
Msg1 = The string parameter is required.
Msg2 = Credentials are required for this command.
Msg3 = The specified variable does not exist.
'@
ConvertFrom-StringData -StringData $Here
```

```Output
Name                           Value
----                           -----
Msg3                           The specified variable does not exist.
Msg2                           Credentials are required for this command.
Msg1                           The string parameter is required.
```

### Exemplo 2: converter dados de cadeia de caracteres usando um delimitador diferente

Este exemplo mostra como converter dados de cadeia de caracteres que usam um caractere diferente como um delimitador. Neste exemplo, os dados de cadeia de caracteres estão usando o caractere de barra vertical ( `|` ) como o delimitador.

```powershell
$StringData = @'
color|red
model|coupe
year|1965
condition|mint
'@
$carData = ConvertFrom-StringData -StringData $StringData -Delimiter '|'
$carData
```

```Output
Name                           Value
----                           -----
condition                      mint
model                          coupe
color                          red
year                           1965
```

### Exemplo 3: converter uma cadeia de caracteres aqui contendo um comentário

Este exemplo converte uma cadeia de caracteres aqui que contém um comentário e vários pares de chave/valor em uma tabela de hash.

```powershell
ConvertFrom-StringData -StringData @'
Name = Disks.ps1

# Category is optional.

Category = Storage
Cost = Free
'@
```

```Output
Name                           Value
----                           -----
Cost                           Free
Category                       Storage
Name                           Disks.ps1
```

O valor do parâmetro **StringData** é uma cadeia de caracteres here, em vez de uma variável que contém uma cadeia de caracteres here. Qualquer um dos dois formatos é válido. A cadeia de caracteres here inclui um comentário sobre uma das cadeias de caracteres.
`ConvertFrom-StringData` ignora comentários de linha única, mas o `#` caractere deve ser o primeiro caractere que não seja espaço em branco na linha. Todos os caracteres na linha após o `#` são ignorados.

### Exemplo 4: converter uma cadeia de caracteres em uma tabela de hash

Este exemplo converte uma cadeia de caracteres entre aspas duplas (não uma cadeia de caracteres aqui) em uma tabela de hash e a salva na `$A` variável.

```powershell
$A = ConvertFrom-StringData -StringData "Top = Red `n Bottom = Blue"
$A
```

```Output
Name             Value
----             -----
Bottom           Blue
Top              Red
```

Para satisfazer a condição de que cada par chave-valor deve estar em uma linha separada, a cadeia de caracteres usa o caractere de nova linha ( \` n) do PowerShell para separar os pares.

### Exemplo 5: usar ConvertFrom-StringData na seção de dados de um script

Este exemplo mostra um `ConvertFrom-StringData` comando usado na seção de dados de um script.
As instruções abaixo da seção DATA exibem o texto para o usuário.

```powershell
$TextMsgs = DATA {
ConvertFrom-StringData @'
Text001 = The $Notebook variable contains the name of the user's system notebook.
Text002 = The $MyNotebook variable contains the name of the user's private notebook.
'@
}
$TextMsgs
```

```Output
Name             Value
----             -----
Text001          The $Notebook variable contains the name of the user's system notebook.
Text002          The $MyNotebook variable contains the name of the user's private notebook.
```

Já que o texto inclui nomes de variáveis, ele deve ser colocado em uma cadeia de caracteres entre aspas simples, de modo que as variáveis sejam interpretadas literalmente e não expandidas. Não são permitidas variáveis na seção **Data** .

### Exemplo 6: usar o operador de pipeline para passar uma cadeia de caracteres

Este exemplo mostra que você pode usar um operador de pipeline ( `|` ) para enviar uma cadeia de caracteres para `ConvertFrom-StringData` . O valor da `$Here` variável é canalizado para `ConvertFrom-StringData` e o resultado na `$Hash` variável.

```powershell
$Here = @'
Msg1 = The string parameter is required.
Msg2 = Credentials are required for this command.
Msg3 = The specified variable does not exist.
'@
$Hash = $Here | ConvertFrom-StringData
$Hash
```

```Output
Name     Value
----     -----
Msg3     The specified variable does not exist.
Msg2     Credentials are required for this command.
Msg1     The string parameter is required.
```

### Exemplo 7: usar caracteres de escape para adicionar novas linhas e caracteres de retorno

Este exemplo mostra o uso de caracteres de escape para criar novas linhas e caracteres de retorno em dados de origem. A sequência de escape `\n` é usada para criar novas linhas dentro de um bloco de texto associado a um nome ou item na tabela de hash resultante.

```powershell
ConvertFrom-StringData @"
Vincentio = Heaven doth with us as we with torches do,\nNot light them for themselves; for if our virtues\nDid not go forth of us, 'twere all alike\nAs if we had them not.
Angelo = Let there be some more test made of my metal,\nBefore so noble and so great a figure\nBe stamp'd upon it.
"@ | Format-List
```

```Output
Name  : Angelo
Value : Let there be some more test made of my metal,
        Before so noble and so great a figure
        Be stamp'd upon it.

Name  : Vincentio
Value : Heaven doth with us as we with torches do,
        Not light them for themselves; for if our virtues
        Did not go forth of us, 'twere all alike
        As if we had them not.
```

### Exemplo 8: usar o caractere de escape de barra invertida para renderizar corretamente um caminho de arquivo

Este exemplo mostra como usar o caractere de escape de barra invertida nos dados de cadeia de caracteres para permitir que um caminho de arquivo seja renderizado corretamente na `ConvertFrom-StringData` tabela de hash resultante. As duas barras invertidas garantem que os caracteres de barra invertida literal sejam processados corretamente na saída da tabela de hash.

```powershell
ConvertFrom-StringData "Message=Look in c:\\Windows\\System32"
```

```Output
Name                           Value
----                           -----
Message                        Look in c:\Windows\System32
```

## PARAMETERS

### -StringData

Especifica a cadeia de caracteres a ser convertida. Você pode usar esse parâmetro ou canalizar uma cadeia de caracteres para `ConvertFrom-StringData` . O nome do parâmetro é opcional.

O valor desse parâmetro deve ser uma cadeia de caracteres que contenha um ou mais pares chave-valor. Cada par chave-valor deve estar em uma linha separada, ou cada par deve ser separado por caracteres de nova linha ( \` n).

Você pode incluir comentários na cadeia de caracteres, mas os comentários não podem estar na mesma linha que um par chave-valor. `ConvertFrom-StringData` ignora comentários de linha única. O `#` caractere deve ser o primeiro caractere que não seja espaço em branco na linha. Todos os caracteres na linha após o `#` são ignorados. Os comentários não são incluídos na tabela de hash.

Uma cadeia de caracteres aqui é uma cadeia de caracteres que consiste em uma ou mais linhas. As aspas na cadeia de caracteres aqui são interpretadas literalmente como parte dos dados da cadeia de caracteres. Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Delimitador

O caractere usado para separar a **chave** dos dados de **valor** na cadeia de caracteres que está sendo convertida.
O delimitador padrão é o caractere de sinal de igual ( `=` ). Esse parâmetro foi adicionado no PowerShell 7.

```yaml
Type: System.Char
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: '='
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres que contém um par chave-valor para `ConvertFrom-StringData` .

## SAÍDAS

### System.Collections.Hashtable

Esse cmdlet retorna uma tabela de hash que ele cria a partir dos pares chave-valor.

## OBSERVAÇÕES

Uma cadeia de caracteres here é uma cadeia de caracteres com uma ou mais linhas, nas quais as aspas são interpretadas literalmente.

Esse cmdlet pode ser útil em scripts que exibem mensagens do usuário em vários idiomas falados. Você pode usar as tabelas de hash em estilo de dicionário para isolar as cadeias de caracteres de texto do código como ocorre em arquivos de recursos, além de formatar as cadeias de caracteres de texto para uso em ferramentas de tradução.

## LINKS RELACIONADOS

