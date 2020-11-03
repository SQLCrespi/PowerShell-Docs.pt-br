---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Date
ms.openlocfilehash: f550d352ca6e400307feba9ec16cea4632603b62
ms.sourcegitcommit: ea9270bacee7dd1b9df2519384de277576357ce2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/25/2020
ms.locfileid: "93195264"
---
# Get-Date

## SINOPSE
Obtém a data e hora atuais.

## SYNTAX

### NET (padrão)

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-Format <String>] [<CommonParameters>]
```

### UFormat

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-UFormat <String>] [<CommonParameters>]
```

## DESCRIPTION

O `Get-Date` cmdlet obtém um objeto **DateTime** que representa a data atual ou uma data que você especifica. `Get-Date` pode formatar a data e a hora em vários formatos .NET e UNIX. Você pode usar `Get-Date` para gerar uma cadeia de caracteres de caractere de data ou hora e, em seguida, enviar a cadeia de caracteres para outros cmdlets ou programas.

`Get-Date` usa as configurações de cultura do computador para determinar como a saída é formatada. Para exibir as configurações do computador, use `(Get-Culture).DateTimeFormat` .

## EXEMPLOS

### Exemplo 1: obter a data e a hora atuais

Neste exemplo, `Get-Date` exibe a data e hora atuais do sistema. A saída está nos formatos de longa data e de hora longa.

```powershell
Get-Date
```

```Output
Tuesday, June 25, 2019 14:53:32
```

### Exemplo 2: obter elementos da data e hora atuais

Este exemplo mostra como usar `Get-Date` para obter o elemento Date ou time. O parâmetro usa os argumentos **Date** , **time** ou **DateTime** .

```powershell
Get-Date -DisplayHint Date
```

```Output
Tuesday, June 25, 2019
```

`Get-Date` usa o parâmetro **DisplayHint** com o argumento **Date** para obter apenas a data.

### Exemplo 3: obter a data e a hora com um especificador de formato .NET

Neste exemplo, um especificador de formato .NET é usado para personalizar o formato da saída. A saída é um objeto de **cadeia de caracteres** .

```powershell
Get-Date -Format "dddd MM/dd/yyyy HH:mm K"
```

```Output
Tuesday 06/25/2019 16:17 -07:00
```

`Get-Date` usa o parâmetro **Format** para especificar vários especificadores de formato.

Os especificadores de formato .NET usados neste exemplo são definidos da seguinte maneira:

| Especificador | Definição |
| --- | --- |
| `dddd` | Dia da semana-nome completo |
| `MM` | Número do mês |
| `dd` | Dia do mês-2 dígitos |
| `yyyy` | Ano no formato de 4 dígitos |
| `HH:mm` | Tempo no formato de 24 horas-sem segundos |
| `K` | Deslocamento de fuso horário da coordenada de tempo universal (UTC) |

Para obter mais informações sobre especificadores de formato .NET, consulte [cadeias de caracteres de formato personalizado de data e hora](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).

### Exemplo 4: obter a data e a hora com um especificador UFormat

Neste exemplo, vários especificadores de formato **uFormat** são usados para personalizar o formato da saída.
A saída é um objeto de **cadeia de caracteres** .

```powershell
Get-Date -UFormat "%A %m/%d/%Y %R %Z"
```

```Output
Tuesday 06/25/2019 16:19 -07
```

`Get-Date` usa o parâmetro **uFormat** para especificar vários especificadores de formato.

Os especificadores de formato **uFormat** usados neste exemplo são definidos da seguinte maneira:

| Especificador | Definição |
| --- | --- |
| `%A` | Dia da semana-nome completo |
| `%m` | Número do mês |
| `%d` | Dia do mês-2 dígitos |
| `%Y` | Ano no formato de 4 dígitos |
| `%R` | Tempo no formato de 24 horas-sem segundos |
| `%Z` | Deslocamento de fuso horário da coordenada de tempo universal (UTC) |

Para obter uma lista de especificadores de formato **uFormat** válidos, consulte a seção [observações](#notes) .

### Exemplo 5: obter o dia do ano de uma data

Neste exemplo, uma propriedade é usada para obter o dia numérico do ano.

O calendário gregoriano tem 365 dias, exceto os anos bissextos que têm 366 dias. Por exemplo, 31 de dezembro de 2020 é o dia 366.

```powershell
(Get-Date -Year 2020 -Month 12 -Day 31).DayOfYear
```

```Output
366
```

`Get-Date` usa três parâmetros para especificar a data: **ano** , **mês** e **dia** . O comando é encapsulado com parênteses para que o resultado seja avaliado pela propriedade **DayofYear** .

### Exemplo 6: verificar se uma data está ajustada para o horário de verão

Este exemplo usa um método booliano para verificar se uma data é ajustada pelo horário de verão.

```powershell
$DST = Get-Date
$DST.IsDaylightSavingTime()
```

```Output
True
```

Uma variável, `$DST` armazena o resultado de `Get-Date` . `$DST` usa o método **IsDaylightSavingTime** para testar se a data é ajustada para o horário de verão.

### Exemplo 7: converter a hora atual em hora UTC

Neste exemplo, a hora atual é convertida em hora UTC. O deslocamento UTC para a localidade do sistema é usado para converter a hora. Uma tabela na seção [observações](#notes) lista os especificadores de formato **uFormat** válidos.

```powershell
Get-Date -UFormat "%A %B/%d/%Y %T %Z"
$Time = Get-Date
$Time.ToUniversalTime()
```

```Output
Wednesday June/26/2019 10:45:26 -07

Wednesday, June 26, 2019 17:45:26
```

`Get-Date` usa o parâmetro **uFormat** com especificadores de formato para exibir a data e a hora atuais do sistema. O especificador de formato **% Z** representa o deslocamento UTC de **-07** .

A `$Time` variável armazena a data e a hora atuais do sistema. `$Time` usa o método **ToUniversalTime ()** para converter a hora com base no deslocamento UTC do computador.

### Exemplo 8: criar um carimbo de data/hora

Neste exemplo, um especificador de formato cria um objeto de **cadeia de caracteres** de carimbo de data/hora para um nome de diretório. O timestamp inclui a data, a hora e o deslocamento UTC.

```powershell
$timestamp = Get-Date -Format o | ForEach-Object { $_ -replace ":", "." }
New-Item -Path C:\Test\$timestamp -Type Directory
```

```Output
    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         6/27/2019    07:59                2019-06-27T07.59.24.4603750-07.00
```

A `$timestamp` variável armazena os resultados de um `Get-Date` comando. `Get-Date` usa o parâmetro **Format** com o especificador de formato de minúsculas `o` para criar um objeto de **cadeia de caracteres** de carimbo de data/hora. O objeto é enviado ao pipeline para `ForEach-Object` . Um **scriptblock** contém a `$_` variável que representa o objeto de pipeline atual. A cadeia de caracteres de carimbo de data/hora é delimitada por dois-pontos que são substituídos por pontos.

`New-Item` usa o parâmetro **path** para especificar o local de um novo diretório. O caminho inclui a `$timestamp` variável como o nome do diretório. O parâmetro de **tipo** especifica que um diretório é criado.

## PARAMETERS

### -Data

Especifica uma data e hora. O tempo é opcional e, se não for especificado, retornará 00:00:00.

Insira a data e a hora em um formato padrão para a localidade do sistema.

Por exemplo, em inglês americano:

`Get-Date -Date "6/25/2019 12:30:22"` Retorna terça-feira, 25 de junho de 2019 12:30:22

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases: LastWriteTime

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Dia

Especifica o dia do mês que é exibido. Insira um valor de 1 a 31.

Se o valor especificado for maior que o número de dias em um mês, o PowerShell adicionará o número de dias ao mês. Por exemplo, `Get-Date -Month 2 -Day 31` exibe **3 de março** , não **31 de fevereiro** .

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayHint

Determina quais elementos de data e hora são exibidos.

Os valores aceitos são os seguintes:

- **Data** : exibe somente a data
- **Hora** : exibe apenas a hora
- **DateTime** : exibe a data e a hora

```yaml
Type: Microsoft.PowerShell.Commands.DisplayHintType
Parameter Sets: (All)
Aliases:
Accepted values: Date, Time, DateTime

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Formato

Exibe a data e hora no formato do Microsoft .NET Framework indicado pelo especificador de formato.
O parâmetro **Format** gera um objeto **String** .

Para obter uma lista de especificadores de formato .NET disponíveis, consulte [cadeias de caracteres de formato personalizado de data e hora](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).

Quando o parâmetro **Format** é usado, `Get-Date` obtém apenas as propriedades do objeto **DateTime** necessárias para exibir a data. Como resultado, algumas das propriedades e métodos de objetos **DateTime** podem não estar disponíveis.

A partir do PowerShell 5,0, você pode usar os seguintes formatos adicionais como valores para o parâmetro de **formato** .

- **Data de início** . Uma representação amigável de arquivo ou caminho da data atual na hora local. O formato é `yyyyMMdd` (diferencia maiúsculas de minúsculas, usando um ano de 4 dígitos, um mês de 2 dígitos e um dia de 2 dígitos). Por exemplo:
  20190627.

- **FileDateUniversal** . Uma representação amigável de arquivo ou caminho da data atual em tempo universal (UTC). O formato é `yyyyMMddZ` (diferencia maiúsculas de minúsculas, usando um ano de 4 dígitos, um mês de 2 dígitos, um dia de 2 dígitos e a letra `Z` como o indicador UTC). Por exemplo: 20190627Z.

- **FileDateTime** . Uma representação de arquivo ou de caminho amigável da data e hora atuais na hora local, no formato de 24 horas. O formato é `yyyyMMddTHHmmssffff` (diferencia maiúsculas de minúsculas, usando um ano de 4 dígitos, um mês de 2 dígitos, um dia de 2 dígitos, a letra `T` como um separador de hora, hora de 2 dígitos, minuto de 2 dígitos, segundo de 2 dígitos e milissegundo de 4 dígitos). Por exemplo: 20190627T0840107271.

- **FileDateTimeUniversal** . Uma representação amigável de arquivo ou caminho da data e hora atuais em UTC (hora universal), no formato de 24 horas. O formato é `yyyyMMddTHHmmssffffZ` (diferencia maiúsculas de minúsculas, usando um ano de 4 dígitos, um mês de 2 dígitos, um dia de 2 dígitos, a letra `T` como um separador de hora, hora de 2 dígitos, minuto de 2 dígitos, segundo de 2 dígitos, milissegundo de 4 dígitos e a letra `Z` como o indicador UTC). Por exemplo: 20190627T1540500718Z.

```yaml
Type: System.String
Parameter Sets: net
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Hora

Especifica a hora que é exibida. Insira um valor de 0 a 23.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Milissegundo

Especifica os milissegundos na data. Insira um valor de 0 a 999.

Esse parâmetro foi introduzido no PowerShell 3,0.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Minuto

Especifica o minuto que é exibido. Insira um valor de 0 a 59.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mês

Especifica o mês que é exibido. Insira um valor de 1 a 12.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Segundo

Especifica o segundo que é exibido. Insira um valor de 0 a 59.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UFormat

Exibe a data e hora no formato UNIX. O parâmetro **uFormat** gera um objeto de cadeia de caracteres.

Os especificadores **uFormat** são precedidos por um sinal de porcentagem ( `%` ), por exemplo,, `%m` `%d` e `%Y` . A seção [observações](#notes) contém uma tabela de **especificadores uFormat** válidos.

Quando o parâmetro **uFormat** é usado, `Get-Date` obtém apenas as propriedades do objeto **DateTime** necessárias para exibir a data. Como resultado, algumas das propriedades e métodos de objetos **DateTime** podem não estar disponíveis.

```yaml
Type: System.String
Parameter Sets: UFormat
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ano

Especifica o ano que é exibido. Insira um valor de 1 a 9999.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Entrada de pipeline

`Get-Date` aceita a entrada do pipeline. Por exemplo, `Get-ChildItem | Get-Date`.

## SAÍDAS

### System. DateTime ou System. String

`Get-Date` Retorna um objeto **DateTime** , exceto quando os parâmetros **Format** e **uFormat** são usados. Os parâmetros **Format** ou **uFormat** retornam objetos de **cadeia de caracteres** .

Quando um objeto **DateTime** é enviado ao pipeline para um cmdlet como o `Add-Content` que espera entrada de cadeia de caracteres, o PowerShell converte o objeto em um objeto de cadeia de **caracteres** .

O método `(Get-Date).ToString()` converte um objeto **DateTime** em um objeto **String** .

Para exibir as propriedades e os métodos de um objeto, envie o objeto para baixo no pipeline para `Get-Member` .
Por exemplo, `Get-Date | Get-Member`.

## OBSERVAÇÕES

Os objetos **DateTime** estão em formatos de data e hora longa para a localidade do sistema.

Os **especificadores uFormat** válidos são exibidos na tabela a seguir:

| Especificador de formato |                                 Significado                     |         Exemplo          |
| ---- | ----------------------------------------------------------------------- | ------------------------ |
| `%A` | Dia da semana-nome completo                                             | Monday                   |
| `%a` | Dia da semana-nome abreviado                                      | Mon                      |
| `%B` | Nome do mês-completo                                                       | Janeiro                  |
| `%b` | Nome do mês-abreviado                                                | Jan                      |
| `%C` | Anos                                                                 | 20 para 2019              |
| `%c` | Data e hora abreviadas                                             | Quinta-feira-Jun 27 08:44:18 2019 |
| `%D` | Data no formato mm/dd/aa                                                 | 06/27/19                 |
| `%d` | Dia do mês-2 dígitos                                             | 05                       |
| `%e` | Dia do mês-dígito precedido por um espaço                            | \<space\>05               |
| `%G` | O mesmo que ' Y '                                                             |                          |
| `%g` | O mesmo que ' y '                                                             |                          |
| `%H` | Hora no formato de 24 horas                                                  | 17                       |
| `%h` | Mesmo que ' b '                                                             |                          |
| `%I` | Hora no formato de 12 horas                                                  | 05                       |
| `%j` | Dia do ano                                                         | 1-366                    |
| `%k` | Mesmo que ' H '                                                             |                          |
| `%l` | O mesmo que ' I ' (I maiúsculo)                                              | 05                       |
| `%M` | minutos                                                                 | 35                       |
| `%m` | Número do mês                                                            | 06                       |
| `%n` | caractere de nova linha                                                       |                          |
| `%p` | AM ou PM                                                                |                          |
| `%R` | Tempo no formato de 24 horas-sem segundos                                      | 17:45                    |
| `%r` | Hora no formato de 12 horas                                                  | 09:15:36 AM              |
| `%S` | Segundos                                                                 | 05                       |
| `%s` | Segundos decorridos desde 1º de janeiro de 1970 00:00:00                          | 1150451174,95705         |
| `%t` | Caractere de tabulação horizontal                                                |                          |
| `%T` | Tempo no formato de 24 horas                                                  | 17:45:52                 |
| `%U` | Mesmo que ' W '                                                             |                          |
| `%u` | Dia da semana-número                                                | Domingo = 0               |
| `%V` | Semana do ano                                                        | 01-53                    |
| `%w` | Mesmo que ' u '                                                             |                          |
| `%W` | Semana do ano                                                        | 00-52                    |
| `%X` | Igual a ' T'                                                             |                          |
| `%x` | Data no formato padrão para localidade                                      | 06/27/19 para inglês-EUA  |
| `%Y` | Ano no formato de 4 dígitos                                                  | 2019                     |
| `%y` | Ano no formato de 2 dígitos                                                  | 19                       |
| `%Z` | Deslocamento de fuso horário da coordenada de tempo universal (UTC)                   | -07                      |

## LINKS RELACIONADOS

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[Get-Culture](Get-Culture.md)

[Get-Member](Get-Member.md)

[New-Item](../Microsoft.PowerShell.Management/New-Item.md)

[New-TimeSpan](New-TimeSpan.md)

[Set-Date](Set-Date.md)
