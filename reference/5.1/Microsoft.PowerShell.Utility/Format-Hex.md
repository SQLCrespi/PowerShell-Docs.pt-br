---
external help file: Microsoft.PowerShell.Utility-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-hex?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Hex
ms.openlocfilehash: 514a66ebee3827de998622a738c75d4f8e0c7279
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193823"
---
# Format-Hex

## SINOPSE

Exibe um arquivo ou outra entrada como hexadecimal.

## SYNTAX

### Caminho (padrão)

```
Format-Hex [-Path] <string[]> [<CommonParameters>]
```

### LiteralPath

```
Format-Hex -LiteralPath <string[]> [<CommonParameters>]
```

### ByInputObject

```
Format-Hex -InputObject <Object> [-Encoding <string>] [-Raw] [<CommonParameters>]
```

## DESCRIPTION

O `Format-Hex` cmdlet exibe um arquivo ou outra entrada como valores hexadecimais. Para determinar o deslocamento de um caractere da saída, adicione o número na extrema esquerda da linha ao número na parte superior da coluna para esse caractere.

O `Format-Hex` cmdlet pode ajudá-lo a determinar o tipo de arquivo de um arquivo corrompido ou um arquivo que pode não ter uma extensão filename. Você pode executar esse cmdlet e, em seguida, ler a saída hexadecimal para obter informações do arquivo.

Ao usar `Format-Hex` em um arquivo, o cmdlet ignora os caracteres de nova linha e retorna todo o conteúdo de um arquivo em uma cadeia de caracteres com a nova linha preservada.

## EXEMPLOS

### Exemplo 1: obter a representação hexadecimal de uma cadeia de caracteres

Esse comando retorna os valores hexadecimais de uma cadeia de caracteres.

```powershell
'Hello World' | Format-Hex
```

```Output
           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   48 65 6C 6C 6F 20 57 6F 72 6C 64                 Hello World
```

A cadeia de caracteres **Olá, mundo** é enviada ao pipeline para o `Format-Hex` cmdlet. A saída hexadecimal de `Format-Hex` mostra os valores de cada caractere na cadeia de caracteres.

### Exemplo 2: localizar um tipo de arquivo da saída hexadecimal

Este exemplo usa a saída hexadecimal para determinar o tipo de arquivo. O cmdlet exibe o caminho completo do arquivo e os valores hexadecimais.

Para testar o comando a seguir, faça uma cópia de um arquivo PDF existente no computador local e renomeie o arquivo copiado para **File. t7f** .

```powershell
Format-Hex -Path .\File.t7f
```

```Output
           Path: C:\Test\File.t7f

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   25 50 44 46 2D 31 2E 35 0D 0A 25 B5 B5 B5 B5 0D  %PDF-1.5..%????.
00000010   0A 31 20 30 20 6F 62 6A 0D 0A 3C 3C 2F 54 79 70  .1 0 obj..<</Typ
00000020   65 2F 43 61 74 61 6C 6F 67 2F 50 61 67 65 73 20  e/Catalog/Pages
```

O `Format-Hex` cmdlet usa o parâmetro **Path** para especificar um nome de arquivo no diretório atual, `File.t7f` . A extensão do arquivo `.t7f` não é comum, mas a saída hexadecimal `%PDF` mostra que se trata de um arquivo PDF.

### Exemplo 3: Exibir saída hexadecimal bruta

Por padrão, o é `Format-Hex` usado para a saída compacta de tipos de dados numéricos: sequências de byte único ou de byte duplo são usadas se o valor for pequeno o suficiente. O parâmetro **RAW** desativa esse comportamento.

```
PS> 1,2,3,1000 | Format-Hex

           Path:

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   01 02 03 E8 03                                   ...è.


PS> 1,2,3,1000 | Format-Hex -Raw

           Path:

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   01 00 00 00 02 00 00 00 03 00 00 00 E8 03 00 00  ............è...
```

Observe a diferença na saída. O parâmetro **RAW** exibe os números como valores de 4 bytes, verdadeiros para seus tipos **Int32** .

## PARAMETERS

### -Codificação

Especifica a codificação da saída. Isso se aplica somente à `[string]` entrada. O parâmetro não tem nenhum efeito sobre tipos numéricos. O valor padrão é `ASCII`.

Os valores aceitáveis para esse parâmetro são os seguintes:

- `Ascii` Usa conjunto de caracteres ASCII (7 bits).
- `BigEndianUnicode` Usa UTF-16 com a ordem de bytes big-endian.
- `Unicode` Usa UTF-16 com a ordem de byte little-endian.
- `UTF7` Usa UTF-7.
- `UTF8` Usa UTF-8.
- `UTF32` Usa UTF-32 com a ordem de byte little-endian.

Os caracteres não ASCII na entrada são gerados como caracteres literais, `?` resultando em uma perda de informações.

```yaml
Type: System.String
Parameter Sets: ByInputObject
Aliases:
Accepted values: ASCII, BigEndianUnicode, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: ASCII
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Usado para entrada de pipeline. A entrada do pipeline dá suporte a apenas determinados tipos e instâncias escalares `[system.io.fileinfo]` para a tubulação `Get-ChildItem` .

Os tipos escalares com suporte são:

- `[string]`
- `[byte]`
- `[int]`, `[int32]`
- `[long]`, `[int64]`

```yaml
Type: System.Object
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LiteralPath

Especifica o caminho completo para um arquivo. O valor de **LiteralPath** é usado exatamente como é digitado.
Esse parâmetro não aceita caracteres curinga. Para especificar vários caminhos para arquivos, separe os caminhos com uma vírgula. Se o parâmetro **LiteralPath** incluir caracteres de escape, coloque o caminho entre aspas simples. O PowerShell não interpreta nenhum caractere em uma única cadeia de caracteres entre aspas como sequências de escape. Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Especifica o caminho para os arquivos. Use um ponto ( `.` ) para especificar o local atual. O caractere curinga ( `*` ) é aceito e pode ser usado para especificar todos os itens em um local. Se o parâmetro **path** incluir caracteres de escape, coloque o caminho entre aspas simples. Para especificar vários caminhos para arquivos, separe os caminhos com uma vírgula.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -RAW

Por padrão, o é `Format-Hex` usado para a saída compacta de tipos de dados numéricos: sequências de byte único ou de byte duplo são usadas se o valor for pequeno o suficiente. O parâmetro **RAW** desativa esse comportamento.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ByInputObject
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

### System.String

É possível canalizar uma cadeia de caracteres para este cmdlet.

## SAÍDAS

### Microsoft. PowerShell. Commands. Bytecollection

Esse cmdlet retorna um **bytecollection** . Esse objeto representa uma coleção de bytes. Ele inclui métodos que convertem a coleção de bytes em uma cadeia de caracteres formatada como cada linha de saída retornada por `Format-Hex` . Se você especificar o **caminho** ou o parâmetro **LiteralPath** , o objeto também conterá o caminho do arquivo que contém cada byte.

## OBSERVAÇÕES

A coluna mais à direita da saída tenta renderizar os bytes como caracteres:

Em geral, cada byte é interpretado como um ponto de código Unicode, o que significa que:

- Caracteres ASCII imprimíveis sempre são renderizados corretamente
- Caracteres UTF-8 de vários bytes nunca são renderizados corretamente
- Os caracteres UTF-16 são renderizados corretamente apenas se o byte de ordem superior acontece `NUL` .

## LINKS RELACIONADOS

[about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[Format-Custom](Format-Custom.md)

[Format-List](Format-List.md)

[Format-Table](Format-Table.md)

[Format-Wide](Format-Wide.md)
